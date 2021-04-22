---
title: /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/sdk/RequestEngine.java

---
# /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/sdk/RequestEngine.java

## Namespaces

| Name           |
| -------------- |
| **[com._4paradigm.hybridse.sdk](/hybridse/usage/api/java/Namespaces/namespacecom_1_1__4paradigm_1_1hybridse_1_1sdk.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[com._4paradigm.hybridse.sdk.RequestEngine](/hybridse/usage/api/java/Classes/classcom_1_1__4paradigm_1_1hybridse_1_1sdk_1_1_request_engine.md)** <br>SQL Engine in request mode.  |




## Source code

```cpp
/*
 * Copyright 2021 4Paradigm
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 * http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */

package com._4paradigm.hybridse.sdk;

import com._4paradigm.hybridse.base.BaseStatus;
import com._4paradigm.hybridse.type.TypeOuterClass;
import com._4paradigm.hybridse.vm.CompileInfo;
import com._4paradigm.hybridse.vm.Engine;
import com._4paradigm.hybridse.vm.EngineOptions;
import com._4paradigm.hybridse.vm.PhysicalOpNode;
import com._4paradigm.hybridse.vm.RequestRunSession;
import com._4paradigm.hybridse.vm.SimpleCatalog;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class RequestEngine implements AutoCloseable {

    private static final Logger logger = LoggerFactory.getLogger(SqlEngine.class);

    private SimpleCatalog catalog;
    private EngineOptions options;
    private Engine engine;
    private RequestRunSession session;
    private CompileInfo compileInfo;
    private PhysicalOpNode plan;


    public RequestEngine(String sql, TypeOuterClass.Database database) throws UnsupportedHybridSeException {
        options = new EngineOptions();
        options.set_keep_ir(true);
        options.set_compile_only(true);
        options.set_performance_sensitive(false);
        catalog = new SimpleCatalog();
        session = new RequestRunSession();
        catalog.AddDatabase(database);
        engine = new Engine(catalog, options);

        BaseStatus status = new BaseStatus();
        boolean ok = engine.Get(sql, database.getName(), session, status);
        if (!(ok && status.getMsg().equals("ok"))) {
            throw new UnsupportedHybridSeException("SQL parse error: " + status.getMsg());
        }
        status.delete();
        compileInfo = session.GetCompileInfo();
        plan = compileInfo.GetPhysicalPlan();
    }

    public PhysicalOpNode getPlan() {
        return plan;
    }

    @Override
    public synchronized void close() {
        engine.delete();
        engine = null;

        compileInfo.delete();
        compileInfo = null;

        options.delete();
        options = null;

        plan.delete();
        plan = null;

        session.delete();
        session = null;

        catalog.delete();
        catalog = null;
    }
}
```



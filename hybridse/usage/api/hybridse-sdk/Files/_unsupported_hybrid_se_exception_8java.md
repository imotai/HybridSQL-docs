---
title: /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/sdk/UnsupportedHybridSeException.java

---
# /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/sdk/UnsupportedHybridSeException.java

## Namespaces

| Name           |
| -------------- |
| **[com._4paradigm.hybridse.sdk](/hybridse/usage/api/java/Namespaces/namespacecom_1_1__4paradigm_1_1hybridse_1_1sdk.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[com._4paradigm.hybridse.sdk.UnsupportedHybridSeException](/hybridse/usage/api/java/Classes/classcom_1_1__4paradigm_1_1hybridse_1_1sdk_1_1_unsupported_hybrid_se_exception.md)** <br>The general exception class throw when query unsupported sql.  |




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

public class UnsupportedHybridSeException extends Exception {

    private String message;
    private Throwable cause;

    public UnsupportedHybridSeException(String message) {
        this.message = message;
        this.cause = null;
    }

    public UnsupportedHybridSeException(String message, Throwable cause) {
        this.message = message;
        this.cause = cause;
    }

    public synchronized Throwable getCause() {
        return this.cause;
    }

    @Override
    public String getMessage() {
        return this.message;
    }
}
```




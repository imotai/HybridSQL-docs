---
title: /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/utils/ConfigReader.java

---
# /Users/chenjing/work/4paradigm/HybridSE/java/hybridse-sdk/src/main/java/com/_4paradigm/hybridse/utils/ConfigReader.java

## Namespaces

| Name           |
| -------------- |
| **[com._4paradigm.hybridse.utils](/hybridse/usage/api/java/Namespaces/namespacecom_1_1__4paradigm_1_1hybridse_1_1utils.md)**  |
| **[java.io](/hybridse/usage/api/java/Namespaces/namespacejava_1_1io.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[com._4paradigm.hybridse.utils.ConfigReader](/hybridse/usage/api/java/Classes/classcom_1_1__4paradigm_1_1hybridse_1_1utils_1_1_config_reader.md)**  |




## Source code

```cpp
/*
 * Copyright 2021 4Paradigm
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *   http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */

package com._4paradigm.hybridse.utils;

import java.io.*;

public class ConfigReader {
    public static String readConf(String path) throws Exception{
        BufferedReader reader = null;
        if (path.startsWith("classpath:")) {
            String parsedPath = path.replace("classpath:", "");
            InputStream is = ConfigReader.class.getResourceAsStream(parsedPath);
            InputStreamReader isr = new InputStreamReader(is, "utf-8");
            reader = new BufferedReader(isr);
        }else {
            reader = new BufferedReader(new FileReader(new File(path)));
        }
        StringBuilder builder = new StringBuilder();
        String line = reader.readLine();
        while (line != null) {
            builder.append(line + System.lineSeparator());
            line = reader.readLine();
        }
        return builder.toString();
    }
}
```




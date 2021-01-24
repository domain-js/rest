# @domain.js/rest
Domain.js 项目通用增删改查模块

[![Build status](https://travis-ci.com/domain-js/rest.svg?branch=master)](https://travis-ci.org/domain-js/rest)
[![codecov](https://codecov.io/gh/domain-js/rest/branch/master/graph/badge.svg)](https://codecov.io/gh/domain-js/rest)

# Installation
<pre>npm i @domain.js/rest --save</pre>

# cnf
专属配置名称 `rest`
<pre>无</pre>

# deps
| 名称 | 类型 | 描述 |
| ------ | ---- | ---- |
| errors.resourceDuplicateAdd | Function | rest.add 方法遇到资源重复是会调用改函数返回错误 |
| errors.notAllowed | Function | rest.list 方法相对时间过滤超过最大天数跨度调用该函数返回错误 |
| _| Object | lodash 库包，之所以通过注入的方式是为把版本控制的主动权交给项目 |

Main.Deps = ["logger", "errors", "_", "moment", "mysql", "Sequelize"];

# Usage
| 功能 | 描述 | 样例 |
| ---- | ---- | ---- |
| rest.list | 列表方法 | rest.list(Model, params) |
| rest.remove | 删除某个资源 | rest.remove(model, userId) |
| rest.modify | 修改某个资源 | rest.modify(Model, model, params, isAdmin, cols) |
| rest.add | 添加一个资源 | rest.add(Model, params, isAdmin, cols, { userId, clientIp }) |
| rest.stats | 统计接口 | rest.stats(Model, params, isAdmin, cols, { userId, clientIp }) |

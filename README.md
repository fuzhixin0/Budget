## 系统地址
---

+ 测试环境： [http://192.168.10.2:8086/Portal/PortalPageIndexStart.aspx](http://192.168.10.2:8086/Portal/PortalPageIndexStart.aspx)

+ 模块入口：`经管平台` → `预算管理` 


## 接口信息
---

### 1. 账套管理

+ ### 账套列表

    - 界面

        `经管平台` → `预算管理` → `系统管理` → `账套管理` 

    - 方法

        `GetAccounts()`

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | page | number | 页码 | Y |
        | size | number | 每页条数 | Y |
        | where | string | 筛选条件 | N |
        | sortname | string | 排序字段 | N |
        | sortorder | string | 排序方式 | N |

    - 输出

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | total | int | 总数 |
        | rows | array | 数据 |

        *rows定义：*

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | Code | string | 编码 |
        | Name | string | 名称 |
        | StartDate | string | 开始时间 |
        | EndDate | string | 结束时间 |

    - 实现

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `AccountController.cs` / `GetAccounts()` 

        ![](images/AccountList.png)

+ ### 账套保存

    - 界面

        `经管平台` → `预算管理` → `系统管理` → `账套管理` 

    - 方法

        `Save()`

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | Code | string | 编码 | N |
        | Name | string | 名称 | Y |
        | StartDate | string | 开始时间 | N |
        | EndDate | string | 结束时间 | N |
        | DepCodes | string | 可申请部门编码 | N |
        | Remark | string | 描述 | N |

    - 输出

        `是否成功`

    - 实现

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `AccountController.cs` / `Save()` 

        ![](images/AccountSave.png)


+ ### 账套编辑

    - 界面

        `经管平台` → `预算管理` → `系统管理` → `账套管理` 

    - 方法

        `Edit()`

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | code | string | 编码 | Y |

    - 输出

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | Code | string | 编码 |
        | Name | string | 名称 |
        | StartDate | string | 开始时间 |
        | EndDate | string | 结束时间 |
        | DepCodes | string | 可申请部门编码 |
        | DepNames | string | 可申请部门名称 |
        | Remark | string | 描述 |

    - 实现

        `MCS.XZTown.Budget.Web` / `Controllers` / `AccountController.cs` / `Edit()` 

        ![](images/AccountEdit.png)

+ ### 账套删除

    - 界面位置

        `经管平台` → `预算管理` → `系统管理` → `账套管理` 

    - 方法名

        `Delete()`

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | code | string | 编码 | Y |

    - 输出

        `是否成功`

    - 实现逻辑

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `AccountController.cs` / `Delete()` 

        ![](images/AccountDelete.png)

### 2. 科目管理

+ ### 科目列表

    - 界面位置

        `经管平台` → `预算管理` → `系统管理` → `科目管理` 

    - 方法名

        `GetSubjects()` 

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | page | number | 页码 | Y |
        | size | number | 每页条数 | Y |
        | where | string | 筛选条件 | N |
        | sortname | string | 排序字段 | N |
        | sortorder | string | 排序方式 | N |

    - 输出

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | total | int | 总数 |
        | rows | array | 数据 |

        *rows定义：*

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | Code | string | 编码 |
        | Name | string | 名称 |
        | DepCode | string | 部门编码 |
        | DepName | string | 部门名称 |
        | IsUse | string | 是否启用 |
        | DownTime | string | 失效时间 |
        | Remark | string | 说明 |


    - 实现逻辑

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `SubjectController.cs` / `GetSubjects()`

        ![](images/SubjectList.png)

+ ### 科目保存

    - 界面位置

        `经管平台` → `预算管理` → `系统管理` → `科目管理` 

    - 方法名

        `Save()` 

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | Code | string | 编码 | N |
        | Name | string | 名称 | Y |
        | DepCode | string | 部门编码 | N |
        | DepName | string | 部门名称 | N |
        | IsUse | string | 是否启用 | N |
        | DownTime | string | 失效时间 | N |
        | Remark | string | 说明 | N |

    - 输出

        `是否成功`

    - 实现逻辑

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `SubjectController.cs` / `Save()`

        ![](images/SubjectSave.png)

+ ### 科目编辑

    - 界面位置

        `经管平台` → `预算管理` → `系统管理` → `科目管理` 

    - 方法名

        `Edit()` 

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | code | string | 编码 | Y |

    - 输出

        | 参数名 | 类型 | 说明 |
        | --- | --- | --- |
        | Code | string | 编码 |
        | Name | string | 名称 |
        | DepCode | string | 部门编码 |
        | DepName | string | 部门名称 |
        | IsUse | string | 是否启用 |
        | DownTime | string | 失效时间 |
        | Remark | string | 说明 |


    - 实现逻辑

        `MCS.XZTown.Budget.Web` / `Controllers` / `SubjectController.cs` / `Edit()`

        ![](images/SubjectEdit.png)

+ ### 科目删除

    - 界面位置

        `经管平台` → `预算管理` → `系统管理` → `科目管理` 

    - 方法名

        `Delete()`

    - 输入
  
        | 参数名 | 类型 | 说明 | 必填 |
        | --- | --- | --- | --- |
        | code | string | 编码 | Y |

    - 输出

       `是否成功`

    - 实现逻辑

        `MCS.XZTown.Budget.Web` / `ApiControllers` / `SubjectController.cs` / `Delete()`

        ![](images/SubjectDelete.png)

### 3. 项目管理

+ ### 项目列表


+ ### 项目保存


+ ### 项目编辑


+ ### 项目删除


+ ### 项目查看


+ ### 项目审批


+ ### 项目审批记录


+ ### 项目评价列表


+ ### 项目评价保存


+ ### 项目评价编辑


### 4. 预算管理


+ ### 预算项目列表


+ ### 预算项目详情


+ ### 预算明细列表


+ ### 预算明细保存


+ ### 预算明细删除


+ ### 支出计划列表


+ ### 支出计划保存


+ ### 支出计划删除


+ ### 年度目标列表


+ ### 年度目标保存


+ ### 相关文件列表


+ ### 相关文件保存


+ ### 相关文件删除


+ ### 预算提交


+ ### 预算审批


+ ### 预算审批记录



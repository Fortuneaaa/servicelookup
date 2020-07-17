# servicelookup
通过 k8s 的 api 用户是没办法很快通过 pod 的名字找到对应的 service 的。当然你可以找到这个 pod 的 label，然后去跟 selector 进行比较而确定 service，但做这种逆向查询是非常费时间的。

所以我这里就是写了这样一种 controller，watch 所有的 endpoints 和 pods，来做比对，找到 pod 服务的 service。

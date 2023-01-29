# 生成代码
hz new -idl idl/core.thrift -module github.com/ClubWeGo/douyinBase

> 扩展模块
hz new -idl idl/interaction.thrift -module github.com/ClubWeGo/douyinBase
hz new -idl idl/relation.thrift -module github.com/ClubWeGo/douyinBase

# 删除代码
rm -r ./biz router.go router_gen.go main.go go.mod go.sum .hz .gitignore

# 更新代码
hz update -idl idl/core.thrift

# 拉取依赖
go mod tidy

# 编译代码
go build
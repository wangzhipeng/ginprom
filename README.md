# ginprom

项目Fork ` github.com/Depado/ginprom` 在此基础上增加 Summary 的 label

# demo 
```
func main() {
	r := gin.Default()
	p := ginprom.New(
		ginprom.Engine(r),
		ginprom.Namespace("name"),
		ginprom.Subsystem("sub"),
		ginprom.Path("/metrics"),
	)
	r.Use(p.Instrument())

	r.GET("/hello/:id", func(c *gin.Context) {})
	r.GET("/world/:id", func(c *gin.Context) {})
	r.Run(":8080")
}
```
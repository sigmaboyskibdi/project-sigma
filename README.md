# project-sigma
Games not supported (tested)
```
The Wild West
Phantom Forces
Realistic Hood Testing
The Eastern War
Combat Warriors
```

Run this in your goofy executor

```
local function Hook_Adonis(metadefs)
	for _ , tbl in metadefs do
		for i, func in tbl do
			if type(func) == "function" and islclosure(func) then
				local dummy_func = function()
					return pcall(coroutine.close, coroutine.running())
				end
				hookfunction(func, dummy_func)
			end
		end
	end
end
local function Init_Bypass()
	for i, v in getgc(true) do
		if
			typeof(v) == "table"
			and rawget(v, "indexInstance")
			and rawget(v, "newindexInstance")
			and rawget(v, "namecallInstance")
			and type(rawget(v,"newindexInstance")) == "table"
		then
			if v["newindexInstance"][1] == "kick" then
				Hook_Adonis(v)
			end
		end
	end
end

task.spawn(Init_Bypass)

task.wait(1.5)

loadstring(game:HttpGet("https://raw.githubusercontent.com/sigmaboyskibdi/project-sigma/refs/heads/main/sigmaboy.lua"))()
```

![image](https://github.com/user-attachments/assets/d6d69627-dc2f-41a8-9df6-9776259c091c)


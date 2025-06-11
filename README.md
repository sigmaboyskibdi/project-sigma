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
task.spawn(function()
	local function Hook_Adonis(metadefs)
		for _ , tbl in meta_defs do
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
	Init_Bypass()
end)

loadstring(game:HttpGet("https://raw.githubusercontent.com/sigmaboyskibdi/project-sigma/refs/heads/main/sigmaboy.lua"))()
```

![image](https://github.com/user-attachments/assets/ccde2644-5e6f-4982-99d2-b6a988ea8c56)

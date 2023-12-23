- 👋 Hi, I’m @User99gkv
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
User99gkv/User99gkv is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

local clock = os.clock

local am = 1000

local create = table.create

vector = {}

function vector.add(v1, v2)
	assert(#v1 == #v2, "Vectors must be of the same length.")
	local result = {}
	for i, value in ipairs(v1) do
		result[i] = value + v2[i]
	end
	return result
end

function vector.add1(v1, v2)
	assert(#v1 == #v2, "Vectors must be of the same length.")
	local result = create(#v1)
	for i, value in ipairs(v1) do
		result[i] = value + v2[i]
	end
	return result
end

function vector.add2(v1, v2)
	local v1A = #v1
	assert(v1A == #v2, "Vectors must be of the same length.")
	local result = create(v1A)
	for i, value in ipairs(v1) do
		result[i] = value + v2[i]
	end
	return result
end

function vector.add3(v1, v2)
	local v1A = #v1
	if v2[v1A + 1] then error"" end
	local result = create(v1A)
	for i, value in ipairs(v1) do
		result[i] = value + v2[i]
	end
	return result
end

local xnil xnil = nil

function vector.add4(v1, v2)
	local v1A = #v1
	if v2[v1A + 1] then error"" end
	local result = create(v1A, xnil)
	for i, value in ipairs(v1) do
		result[i] = value + v2[i]
	end
	return result
end

function vector.add5(v1, v2)
	local v1A = #v1
	if v2[v1A + 1] then error"" end
	local result = create(v1A, xnil)
	for i = 1, v1A do
		result[i] = v1[i] + v2[i]
	end
	return result
end

local ind = 1

function vector.add6(v1, v2)
	local v1A = #v1
	if v2[v1A + 1] then error"" end
	local result = create(v1A, xnil)
	for i = ind, v1A do
		result[i] = v1[i] + v2[i]
	end
	return result
end

function vector.add7(v1, v2)
	local v1A = #v1
	if v2[v1A + ind] then error"" end
	local result = create(v1A, xnil)
	for i = ind, v1A do
		result[i] = v1[i] + v2[i]
	end
	return result
end

function vector.add8(v1, v2)
	local v1A = #v1
	if v2[v1A + ind] then error"" end
	local result = create(v1A, xnil)
	for i = ind, v1A do
		result[i] = v1[i] + v2[i]
	end
	return result
end

local random = math.random

local vectorMockmt = {
	__add = function(v1, v2)
		return setmetatable({ x = v1.x + v2.x, y = v1.y + v2.y, z = v1.z + v2.z }, getmetatable(v1))
	end
}

local vectorMock1 = setmetatable({ x = 1, y = 1, z = 1}, vectorMockmt)
local vectorMock2 = setmetatable({ x = 1, y = 1, z = 1}, vectorMockmt)

local v1 = create(am, vectorMock1) --Vector3.one)
local v2 = create(am, vectorMock2) --Vector3.one)

print("og")
local elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op1")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add1(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op2")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add2(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op3")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add3(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op4")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add4(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op5")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add5(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op6")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add6(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op7")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add7(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

print("op8")
elapsed = 0
for i = 1, am do
	local start = clock()
	local _ = vector.add8(v1,v2)
	local endT = clock() - start; elapsed = elapsed + endT
end
print(elapsed/ am)

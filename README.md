local validated = true
local validationEvent = Instance.new("BindableEvent")
validationEvent:Fire(true)

local function verifyKey(inputKey)
    return true
end

return {
    WaitForValidation = function()
        return validationEvent.Event:Wait()
    end,
    IsValidated = function()
        return validated
    end,
    CheckKey = verifyKey
}

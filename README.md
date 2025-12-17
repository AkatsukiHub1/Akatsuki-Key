local validated = true

return {
    WaitForValidation = function()
        return validated
    end,
    IsValidated = function()
        return validated
    end,
    CheckKey = function()
        return validated
    end
}

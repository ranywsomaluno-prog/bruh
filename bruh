-- Carregar Rayfield
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Criar Janela
local Window = Rayfield:CreateWindow({
    Name = "Interface de Teste",
    LoadingTitle = "Rayfield UI",
    LoadingSubtitle = "Exemplo Toggle + Slider",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = "RayfieldExample",
        FileName = "ConfigUI"
    }
})

-- Criar Aba
local MainTab = Window:CreateTab("Controle", 4483362458) -- ícone exemplo
local Section = MainTab:CreateSection("Executar Ação")

-- Variáveis de controle
local AutoExecutar = false
local Velocidade = 1 -- tempo em segundos

-- Função simulada (aqui você substituiria pelo que quiser executar)
local function ExecutarAcao()
    print("Executando ação simulada...")
end

-- Toggle para loop
MainTab:CreateToggle({
    Name = "Executar Repetidamente",
    CurrentValue = false,
    Callback = function(Value)
        AutoExecutar = Value
        print("AutoExecutar:", Value)

        if AutoExecutar then
            task.spawn(function()
                while AutoExecutar do
                    ExecutarAcao()
                    task.wait(Velocidade)
                end
            end)
        end
    end,
})

-- Slider para velocidade
MainTab:CreateSlider({
    Name = "Velocidade de Execução",
    Range = {0.1, 5}, -- intervalo mínimo/máximo
    Increment = 0.1,
    Suffix = "s",
    CurrentValue = 1,
    Callback = function(Value)
        Velocidade = Value
        print("Velocidade ajustada para:", Value, "segundos")
    end,
})

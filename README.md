local espEnabled = true

function onUpdate()
    if love.keyboard.isDown("f3") then
        espEnabled = not espEnabled
    end

    if espEnabled then
        for _, enemy in ipairs(getEnemies()) do
            drawSquareAround(enemy)
        end
    end
end

function drawSquareAround(enemy)
    local x, y, width, height = enemy:getBounds()
    love.graphics.setColor(1, 0, 0)
    love.graphics.rectangle("line", x, y, 

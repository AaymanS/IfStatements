-----------------------------------------------------------------------------------------
--
-- main.lua
--
-- Created by: Aayman Shameem
-- Created on: Mar 3 2018
--
-- show how to use an if statement
-- and random numbers
-----------------------------------------------------------------------------------------
display.setDefault( "background", 0.5, 0.05, 0.35 )

local someInputDisplay = display.newText ( "Type in a number from 1 to 6: ", display.contentCenterX - 50, display.contentCenterY - 120, native.systemFont, 30)

local someInputTextField = native.newTextField ( display.contentCenterX + 200, display.contentCenterY - 120, 100, 30 )
someInputTextField.id = "The user input"

local computerNumberDisplay = display.newText ( "Computer's choice: ", display.contentCenterX - 110, display.contentCenterY + 20, native.systemFont, 30)


local guessButton = display.newImageRect( "./assets/sprites/enterButton.png", 150, 75 )
guessButton.x = display.contentCenterX 
guessButton.y = display.contentCenterY - 50
guessButton.id = "guess button"


--[[math.randomseed( os.time() )

local numberToGuess = math.random( 1, 6 )
tonumber( numberToGuess )
local answer 
local answerAsNumber


-- io.write( "Pick a number from 1 to 6: " )

answer=io.read()
answerAsNumber = tonumber("answer")
]]



local function ButtonClick( event )

 	local clear2 = display.newRect(display.contentCenterX + 140, display.contentCenterY + 15, 100, 60)
	clear2:setFillColor(0.5, 0.05, 0.35 )

	local clear1 = display.newRect(display.contentCenterX, display.contentCenterY + 100, 200, 90)
	clear1:setFillColor(0.5, 0.05, 0.35 )

	math.randomseed( os.time() )

	local numberToGuess = math.random( 6 )

	local answerAsNumber = tonumber(someInputTextField.text)


	local compChoice = display.newText ( numberToGuess, display.contentCenterX + 140, display.contentCenterY + 20, native.systemFont, 30 )


	

	-- if the user's number is right, then show "Correct" 
	if numberToGuess == answerAsNumber then

    local rightAnswer = display.newText ( "CORRECT", display.contentCenterX, display.contentCenterY + 100, native.systemFont, 30 )

	-- if the user's number is wrong, then show "Incorrect"
	elseif numberToGuess ~= answerAsNumber then

	local wrongAnswer = display.newText ( "INCORRECT", display.contentCenterX, display.contentCenterY + 120, native.systemFont, 30 )

	end
end

guessButton:addEventListener( "touch", ButtonClick )

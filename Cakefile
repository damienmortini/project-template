fs = require 'fs'
{exec} = require 'child_process'

# Order of files is important
coffeeFiles = [
	'main'
]

outputFile = "public/js/main.js"
strCoffeeFiles = ("coffee/#{file}.coffee" for file in coffeeFiles).join ' '

task 'setup', 'Setup project environment', ->
	setup = exec "coffee -j #{outputFile} -cw #{strCoffeeFiles} & compass watch & cd ./public; python -m SimpleHTTPServer"
	setup.stdout.on 'data', (data)-> process.stdout.write data
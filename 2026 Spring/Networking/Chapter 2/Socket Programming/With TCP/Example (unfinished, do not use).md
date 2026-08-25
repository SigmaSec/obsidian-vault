Python TCP:
From socket import *
serverName = 'servername'
serverPort = 12000
clientSocket = socket(AF_INET, SOCK_STREAM)
clientSocket.connect((serverName,serverPort))
sentence = input('Input lowercase sentence')
clientSocket.send(sentence.encode())
//unfinished.
//I hate how quickly he goes on slides

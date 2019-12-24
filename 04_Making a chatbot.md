### 1. Telegram 을 이용한 채팅봇

<h4> app.py

from flask import Flask, render_template, request

from decouple import config

import random

import requests



app = Flask(__name__)



url = "https://api.telegram.org/bot"

token = config('TELEGRAM_BOT_TOKEN')

chat_id = config('CHAT_ID')



@app.route('/')

def hello():

  return "Hello World"



@app.route('/send')

def send():

  text = request.args.get('text')

  requests.get(f'{url}{token}/sendMessage?chat_id={chat_id}&text={text}')

  return render_template('send.html', text=text)



@app.route('/write')

def write():

  return render_template('write.hteml')



@app.route(f'/{token}' , methods=["POST"])

def telegram():

  data = request.get_json()

  text = data['message']['text']

  chatID = data['message']['chat']['id']

  text = data['message']['text']



  if text == "안녕":

​    return_text = "안녕하세요"

  elif text == "로또":

​    numbers = range(1,46)

​    return_text = sorted(random.sample(numbers, 6))

​    

  else :

​    return_text = "지금 지원하는 채팅은 안녕입니다."



  requests.get(f'{url}{token}/sendMessage?chat_id={chatID}&text={return_text}')

  return "ok" , 200



if __name__ == '__main__':

  app.run(debug=True)





<h4> webhook.py

</h4>

from decouple import config

import requests



token =config('TELEGRAM_BOT_TOKEN')

url = "http://api.telegram.org/bot"

paw_url = 'https://rhkdgus73.pythonanywhere.com'



data =requests.get(f'{url}{token}/setwebhook?url={paw_url}/{token}')



print(data.text)



<h4> env.py

TELEGRAM_BOT_TOKEN="948833977:AAGZLX8vBFOqhErB5UM8dqSepA3Fx_St6l8"
CHAT_ID="956979886"
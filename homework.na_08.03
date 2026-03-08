import time, threading, telebot
from telebot import TeleBot
import random


links = ['https://dzen.ru/a/Yezp5WbK0hMwksj3' , 'https://ria.ru/20260220/moskva-2075744866.html' ,'https://ria.ru/20260219/kostroma-2075503297.html' ]
token = "8263397450:AAEG9A_UUCijklkBJLFnvJQ6lA2kdgbtgO4"
images = ['ekology/image1.jpg' , 'ekology/image2.jpg' , 'ekology/image3.jpg']
recommendations = ['Экономить электроэнергию: выключать свет, когда уходишь из комнаты, использовать LED-лампы — они потребляют меньше энергии, отключать зарядные устройства из розетки после использования.' , 'Сокращать отходы: отказаться от одноразового пластика — покупать многоразовые бутылки, сумки и контейнеры, сортировать мусор — сдавать бумагу, стекло, металл и пластик в переработку. ' , 'Бережно использовать воду: закрывать кран, пока чистишь зубы или намыливаешь посуду, установить аэратор на кран — он снижает расход воды без потери напора, стирать одежду при полной загрузке машинки']
monitoring = ['Погода в Казани -16 градусов' , 'Погода в Москве 0 градусов', ' Погода в Санкт-Петербурге +2 градусов' , 'Погода в Уфе -18 градусов']
bot = telebot.TeleBot("т3т мой токен")
images3 = ['ekology/one.jpg' , 'ekology/two.jpg' , 'ekology/three.jpg']

@bot.message_handler(commands=['start'])
def send_start(message):
    bot.reply_to(message, "Привет! Я твой новый помощник, чтобы ты не засорял планету! Вводи команду /help чтобы узнать что я умею")

@bot.message_handler(commands=['help'])
def send_help(message):
    bot.reply_to(message, '1. /recommendations - дает советы по экологии 2. /news - показывает актуальные новости. 3. /about - Что такое экология?')

@bot.message_handler(commands=['about'])
def send_about(message):
    bot.reply_to(message, 'Экология — естественная наука (раздел биологии) о взаимодействиях живых организмов между собой и с их средой обитания, об организации и функционировании биосистем различных уровней (популяции, сообщества, экосистемы).')

@bot.message_handler(commands=['news'])
def send_news(message):
    bot.reply_to(message, random.choice(links))

@bot.message_handler(commands=['monitoring'])
def send_monitoring(message):
    bot.reply_to(message, random.choice(monitoring))
    img2 = random.choice(images3)
    with open(img2, 'rb') as f:
        bot.send_photo(message.chat.id, f)


@bot.message_handler(commands=['recommendations'])
def send_recommendations(message):
    bot.reply_to(message, random.choice(recommendations)) 
    img = random.choice(images)
    with open(img, 'rb') as f:
        bot.send_photo(message.chat.id, f)


print("Бот запущен")   
bot.polling()

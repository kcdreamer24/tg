import telebot
import os
from telebot import types 
from terms import terms, term1, term2
from impdates import constitutions, hello1
from companylaw1 import informa, informa1
from sudprakt import kp, mena, dar, arenda, lizing, podrad, uslugi, perevozka, celine, komsa, tovar, delikt, kond, nasl, zaem, pravovaya_priroda, forma_soglasheniya, vidy, sootnoshenie_neustoyki_ubitkov

# 🔑 Токен берём из переменной окружения
TOKEN = os.getenv("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def hello(message):
    markup = types.InlineKeyboardMarkup()
    markup.add (types.InlineKeyboardButton("Право", callback_data="law"))
    markup.add (types.InlineKeyboardButton("Термины", callback_data="chinese"))
    text = "\n\n" + '\n'.join(hello1)
    bot.send_message(message.chat.id,text,reply_markup=markup)



@bot.callback_query_handler(func=lambda call: True)
def callback(call):
    bot.answer_callback_query(call.id)
    if call.data == "law":
        markup = types.InlineKeyboardMarkup()
        btn1 = types.InlineKeyboardButton("Право РФ", callback_data="law_rf")
        btn2 = types.InlineKeyboardButton("Право КНР", callback_data="law_cnr")
        btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
        markup.add(btn1, btn2, btn_home)

        bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
        bot.answer_callback_query(call.id)

    elif call.data == "law_cnr":
          markup = types.InlineKeyboardMarkup()
          btn2_1 = types.InlineKeyboardButton('Важные даты', callback_data = 'important_dates') #Про важные даты в Истории Китая
          btn2_2 = types.InlineKeyboardButton('Закон КНР о Компаниях', callback_data = 'lawcompany')
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn2_1,btn2_2, btn_home)

          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "home":
      markup = types.InlineKeyboardMarkup()
      btn1 = types.InlineKeyboardButton("Право", callback_data="law")
      btn2 = types.InlineKeyboardButton("Термины", callback_data="chinese")
      markup.add(btn1, btn2)
      bot.edit_message_text(chat_id=call.message.chat.id,
                          message_id=call.message.message_id,
                          text = "\n\n" + '\n'.join(hello1),
                          reply_markup=markup)
      bot.answer_callback_query(call.id)



    elif call.data == "lawcompany":
          markup = types.InlineKeyboardMarkup()
          btn2_3 = types.InlineKeyboardButton ("Акционерные Компании",callback_data = 'acompany')
          btn2_4 = types.InlineKeyboardButton ("Компании с ограниченной ответственностью",callback_data = 'ocompany')
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn2_3,btn2_4, btn_home)
          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "acompany":
          markup = types.InlineKeyboardMarkup()
          btn3_1 = types.InlineKeyboardButton ('Компетенции', callback_data = 'comp')
          btn3_2 = types.InlineKeyboardButton ('Ответственность', callback_data = 'otv')
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn3_1,btn3_2,btn_home)

          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "otv":
          text = "Ответственность\n\n" + '\n'.join(informa)
          bot.send_message(call.message.chat.id,text, parse_mode='HTML')
          markup = types.InlineKeyboardMarkup()
          markup.add(types.InlineKeyboardButton("Право", callback_data="law"))
          markup.add(types.InlineKeyboardButton("Термины", callback_data="chinese"))
          start_text = "\n\n" + "\n".join(hello1)   # твой стартовый текст
          bot.send_message(call.message.chat.id, start_text, reply_markup=markup)
    elif call.data == "comp":
          text = "Компетенции\n\n" + '\n'.join(informa1)
          bot.send_message(call.message.chat.id,text, parse_mode='HTML')

          markup = types.InlineKeyboardMarkup()
          markup.add(types.InlineKeyboardButton("Право", callback_data="law"))
          markup.add(types.InlineKeyboardButton("Термины", callback_data="chinese"))
          start_text = "\n\n" + "\n".join(hello1)   # твой стартовый текст
          bot.send_message(call.message.chat.id, start_text, reply_markup=markup)


    elif call.data == "important_dates":
          text = "Важные даты:\n\n" + '\n'.join(constitutions)
          bot.send_message(call.message.chat.id,text, parse_mode='HTML')

          markup = types.InlineKeyboardMarkup()
          markup.add(types.InlineKeyboardButton("Право", callback_data="law"))
          markup.add(types.InlineKeyboardButton("Термины", callback_data="chinese"))
          start_text = "\n\n" + "\n".join(hello1)   # твой стартовый текст
          bot.send_message(call.message.chat.id, start_text, reply_markup=markup)

    if call.data == "chinese":
            markup = types.InlineKeyboardMarkup()
            btn1_1 = types.InlineKeyboardButton ("КНР",callback_data="chinese_terms")
            btn1_2 = types.InlineKeyboardButton ("система законодательства",callback_data="chinese_terms_2")
            btn1_3 = types.InlineKeyboardButton ("договоры",callback_data="chinese_terms_3")
            markup.add(btn1_1, btn1_2, btn1_3)

            bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
            bot.answer_callback_query(call.id)
    elif call.data == "chinese_terms":
            text = "КНР:\n\n" + '\n'.join(terms)
            bot.send_message(call.message.chat.id,text)
    elif call.data == "chinese_terms_2":
            text = "система законодательства:\n\n" + '\n'.join(term1)
            bot.send_message(call.message.chat.id,text)
    elif call.data == "chinese_terms_3":
            text = "договоры:\n\n" + '\n'.join(term2)
            bot.send_message(call.message.chat.id,text)

    elif call.data == "law_rf":
          markup = types.InlineKeyboardMarkup()
          btn4 = types.InlineKeyboardButton('Гражданское право', callback_data = 'gk')  
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn4, btn_home)
          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "gk":
          markup = types.InlineKeyboardMarkup()
          btn5 = types.InlineKeyboardButton('Постановления', callback_data = 'postanov') 
          btn55 = types.InlineKeyboardButton('Неустойка', callback_data = 'neust')
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn5, btn55, btn_home)
          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "postanov":
          markup = types.InlineKeyboardMarkup()
          btn5_1 = types.InlineKeyboardButton('Купля-продажа', callback_data = 'kp') 
          btn5_2 = types.InlineKeyboardButton('Мена', callback_data = 'mena') 
          btn5_3 = types.InlineKeyboardButton('Дарение', callback_data = 'dar') 
          btn5_4 = types.InlineKeyboardButton('Аренда', callback_data = 'arenda') 
          btn5_5 = types.InlineKeyboardButton('Лизинг', callback_data = 'lizing') 
          btn5_6 = types.InlineKeyboardButton('Подряд', callback_data = 'podrad') 
          btn5_7 = types.InlineKeyboardButton('Возмездное оказание услуг', callback_data = 'uslugi') 
          btn5_8 = types.InlineKeyboardButton('Перевозка', callback_data = 'perevozka') 
          btn5_9 = types.InlineKeyboardButton('Страхование', callback_data = 'celine') 
          btn5_10 = types.InlineKeyboardButton('Комиссия', callback_data = 'komsa') 
          btn5_11 = types.InlineKeyboardButton('Товарищество', callback_data = 'tovar') 
          btn5_12 = types.InlineKeyboardButton('Деликт', callback_data = 'delikt') 
          btn5_13 = types.InlineKeyboardButton('Кондикция', callback_data = 'kond') 
          btn5_14 = types.InlineKeyboardButton('Наследование', callback_data = 'nasl') 
          btn5_15 = types.InlineKeyboardButton('Заем', callback_data = 'zaem') 
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn5_1,btn5_2,btn5_3,btn5_4,btn5_5,btn5_6,btn5_7,btn5_8,btn5_9,btn5_10,btn5_11,btn5_12,btn5_13,btn5_14,btn5_15, btn_home)
          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "kp":
      text = "\n\n" + '\n'.join(kp)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "mena":
      text = "\n\n" + '\n'.join(mena)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "dar":
      text = "\n\n" + '\n'.join(dar)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "arenda":
      text = "\n\n" + '\n'.join(arenda)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "lizing":
      text = "\n\n" + '\n'.join(lizing)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "podrad":
      text = "\n\n" + '\n'.join(podrad)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "uslugi":
      text = "\n\n" + '\n'.join(uslugi)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "perevozka":
      text = "\n\n" + '\n'.join(perevozka)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "celine":
      text = "\n\n" + '\n'.join(celine)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "komsa":
      text = "\n\n" + '\n'.join(komsa)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "tovar":
      text = "\n\n" + '\n'.join(tovar)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "delikt":
      text = "\n\n" + '\n'.join(delikt)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "kond":
      text = "\n\n" + '\n'.join(kond)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "nasl":
      text = "\n\n" + '\n'.join(nasl)
      bot.send_message(call.message.chat.id,text)
    elif call.data == "zaem":
      text = "\n\n" + '\n'.join(zaem)
      bot.send_message(call.message.chat.id,text)

    elif call.data == "neust":
          markup = types.InlineKeyboardMarkup()
          btn6_1 = types.InlineKeyboardButton('Правовая природа', callback_data = 'pr_pr') 
          btn6_2 = types.InlineKeyboardButton('Форма соглашения', callback_data = 'formasogl') 
          btn6_3 = types.InlineKeyboardButton('Виды', callback_data = 'vidy') 
          btn6_4 = types.InlineKeyboardButton('Соотношение неустойки и убытков', callback_data = 'sootn') 
          btn_home = types.InlineKeyboardButton("🏠 В начало", callback_data="home")
          markup.add(btn6_1,btn6_2,btn6_3,btn6_4,btn_home)
          bot.edit_message_text (chat_id=call.message.chat.id, message_id=call.message.message_id, text="Выберите", reply_markup=markup)
          bot.answer_callback_query(call.id)
    elif call.data == "pr_pr":
      text = "\n\n" + '\n'.join(pravovaya_priroda)
      bot.send_message(call.message.chat.id,text)

    elif call.data == "formasogl":
      text = "\n\n" + '\n'.join(forma_soglasheniya)
      bot.send_message(call.message.chat.id,text)

    elif call.data == "vidy":
      text = "\n\n" + '\n'.join(vidy)
      bot.send_message(call.message.chat.id,text)

    elif call.data == "sootn":
      text = "\n\n" + '\n'.join(sootnoshenie_neustoyki_ubitkov)
      bot.send_message(call.message.chat.id,text)

bot.polling(none_stop=True)

# vk_api__bot_reaction_ids
There is no information on the correspondence of integer values of emoji reaction IDs on the [official documentation page](https://dev.vk.com/ru/method/messages.sendReaction). This repository provides a list obtained experimentally. The experiment code is shown below.
P.S. 

| reaction_id | emoji |
| :---: | :---: |
| 1 | ❤️ |
| 2 | 🔥 |
| 3 | 😂 |
| 4 | 👍 |
| 5 | 💩 |
| 6 | ❓ |
| 7 | 😭 |
| 8 | 😡 |
| 9 | 👎 |
| 10 | 👌 |
| 11 | 😄 |
| 12 | 🤔 |
| 13 | 🙏 |
| 14 | 😘 |
| 15 | 😍 |
| 16 | 🎉 |


P.S. I only identified 16. I got an error on 17. Maybe there are others.

The experiment code:
```python
from vkbottle import Bot
from vkbottle.bot import Message

bot = Bot(
    token="BOT_TOKEN",
)


@bot.on.private_message()
async def cmd_start(message: Message):
    reaction_id = message.text
    await bot.api.messages.send_reaction(
        peer_id=message.peer_id,
        cmid=message.conversation_message_id,
        reaction_id=int(reaction_id),
    )

if __name__ == "__main__":
    bot.run_forever()

```

vkbottle reaction_id reaction_ids send_reaction vk api

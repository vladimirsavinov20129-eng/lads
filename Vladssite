from telegram import Update, InlineKeyboardButton, InlineKeyboardMarkup
from telegram.ext import ApplicationBuilder, CommandHandler, CallbackQueryHandler, ContextTypes

TOKEN = "8791201549:AAG-BW2OELQvcZ6SMqb3ONB9y4zQxRaJCPA"

YOUTUBE = "https://www.youtube.com/@Vladsmp4"
DISCORD = "vlads2626"
TWITCH = "https://www.twitch.tv/Vlads2626"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    keyboard = [
        [InlineKeyboardButton("📺 YouTube", callback_data="youtube")],
        [InlineKeyboardButton("💬 Discord", callback_data="discord")],
        [InlineKeyboardButton("🎮 Twitch", callback_data="twitch")]
    ]

    await update.message.reply_text(
        "🌐 Мои соцсети:",
        reply_markup=InlineKeyboardMarkup(keyboard)
    )

async def button(update: Update, context: ContextTypes.DEFAULT_TYPE):
    query = update.callback_query
    await query.answer()

    if query.data == "youtube":
        await query.edit_message_text(f"📺 YouTube:\n{YOUTUBE}")

    elif query.data == "discord":
        await query.edit_message_text(f"💬 Discord:\n{DISCORD}")

    elif query.data == "twitch":
        await query.edit_message_text(f"🎮 Twitch:\n{TWITCH}")

app = ApplicationBuilder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))
app.add_handler(CallbackQueryHandler(button))

print("Бот запущен...")
app.run_polling()

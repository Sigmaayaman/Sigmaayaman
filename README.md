const fs = require("fs");
const petik = '```'
let setting = JSON.parse(fs.readFileSync('./config.json'))
const { getLimit, getBalance, cekGLimit } = require("../lib/limit")


function toCommas(x) {
    x = x.toString()
    var pattern = /(-?\d+)(\d{3})/;
     while (pattern.test(x))
       x = x.replace(pattern, "$1,$2");
    return x;
}

exports.allMenu = (role, ucapanWaktu, pushname, mundur, upload, download, ownerName, botName, jam, tanggal, runtime, isCreator, isPremium, sender, limitCount, limit, gcount, glimit, balance, prefix) => {
    return`${ucapanWaktu} ${pushname !== undefined ? pushname : 'Kak'}

Hitung Mundur Idul Fitri ðŸŒ™ 
${mundur}

*STATISTICS*
 â€¢ Upload : ${upload}
 â€¢ Downloads : ${download}

*BOT INFO*
 â€¢ Creator : ${ownerName}
 â€¢ Bot Name : ${botName}
 â€¢ Time : ${jam}
 â€¢ Date : ${tanggal(new Date())}
 â€¢ Runtime : ${runtime(process.uptime())}

*USER INFO*
 â€¢ Name : ${pushname !== undefined ? pushname : '-'}
 â€¢ Status : ${isCreator ? 'Owner' : isPremium ? 'Premium' : 'Free'}
 â€¢ Limit : ${isCreator ? 'Unlimited' : isPremium ? 'Unlimited' : getLimit(sender, limitCount, limit)}
 â€¢ Limit Game : ${isCreator ? 'Unlimited' : cekGLimit(sender, gcount, glimit)}
 â€¢ Balance : ${toCommas(getBalance(sender, balance))}
 â€¢ Role : ${role}
 
 
*MAIN MENU*${petik}
 â€¢ ${prefix}menu
 â€¢ ${prefix}infobot
 â€¢ ${prefix}donate
 â€¢ ${prefix}dashboard
 â€¢ ${prefix}owner
 â€¢ ${prefix}cekdrive
 â€¢ ${prefix}cekbandwidth
 â€¢ ${prefix}cekpremium
 â€¢ ${prefix}listpremium
 â€¢ ${prefix}listsewa
 â€¢ ${prefix}speed
 â€¢ ${prefix}runtime
 â€¢ ${prefix}listbahasa${petik}

*CONVERTER/TOOLS*${petik} 
 â€¢ ${prefix}sticker
 â€¢ ${prefix}stickerwm
 â€¢ ${prefix}smeme
 â€¢ ${prefix}toimg
 â€¢ ${prefix}tovideo
 â€¢ ${prefix}tomp3
 â€¢ ${prefix}ttp
 â€¢ ${prefix}attp
 â€¢ ${prefix}emojimix
 â€¢ ${prefix}ai
 â€¢ ${prefix}aiimg
 â€¢ ${prefix}chatgpt
 â€¢ ${prefix}nuliskiri
 â€¢ ${prefix}nuliskanan
 â€¢ ${prefix}foliokiri
 â€¢ ${prefix}foliokanan
 â€¢ ${prefix}say
 â€¢ ${prefix}translate${petik}

*ANONYMOUS CHATS*${petik}
 â€¢ ${prefix}menfess
 â€¢ ${prefix}confess
 â€¢ ${prefix}balasmenfess
 â€¢ ${prefix}tolakmenfess
 â€¢ ${prefix}stopmenfess
 â€¢ ${prefix}anonymous
 â€¢ ${prefix}start
 â€¢ ${prefix}next
 â€¢ ${prefix}stop
 â€¢ ${prefix}sendprofile${petik}

*STORE MENU*${petik}
 â€¢ ${prefix}list
 â€¢ ${prefix}addlist
 â€¢ ${prefix}dellist
 â€¢ ${prefix}update
 â€¢ ${prefix}jeda
 â€¢ ${prefix}tambah
 â€¢ ${prefix}kurang
 â€¢ ${prefix}kali
 â€¢ ${prefix}bagi
 â€¢ ${prefix}delsetdone
 â€¢ ${prefix}changedone
 â€¢ ${prefix}setdone
 â€¢ ${prefix}delsetproses
 â€¢ ${prefix}changeproses
 â€¢ ${prefix}setproses
 â€¢ proses < reply chat >
 â€¢ done < reply chat >${petik}

*RPG GAMES*${petik}
 â€¢ ${prefix}inventory
 â€¢ ${prefix}mining
 â€¢ ${prefix}buy 
 â€¢ ${prefix}sell
 â€¢ ${prefix}heal
 â€¢ ${prefix}hunt
 â€¢ ${prefix}adventure
 â€¢ ${prefix}luckyday
 â€¢ ${prefix}killslime
 â€¢ ${prefix}killgoblin
 â€¢ ${prefix}killdevil
 â€¢ ${prefix}killbehemoth
 â€¢ ${prefix}killdemon
 â€¢ ${prefix}killdemonking
 â€¢ ${prefix}joinrpg
 â€¢ ${prefix}sellikan
 â€¢ ${prefix}sellbesi
 â€¢ ${prefix}sellemas
 â€¢ ${prefix}jelajah
 â€¢ ${prefix}mancing
 â€¢ ${prefix}jualikan
 â€¢ ${prefix}jualcoal
 â€¢ ${prefix}lebur
 â€¢ ${prefix}jualstone
 â€¢ ${prefix}jualingot
 â€¢ ${prefix}jualkayu
 â€¢ ${prefix}nebang
 â€¢ ${prefix}goplanet
 â€¢ ${prefix}jualbahankimia${petik}

*DOWNLOADS MENU*${petik}
 â€¢ ${prefix}play
 â€¢ ${prefix}ytmp3
 â€¢ ${prefix}ytmp4
 â€¢ ${prefix}instagram
 â€¢ ${prefix}igphoto
 â€¢ ${prefix}igvideo
 â€¢ ${prefix}igreels
 â€¢ ${prefix}tiktok
 â€¢ ${prefix}tiktoknowm
 â€¢ ${prefix}tiktokaudio
 â€¢ ${prefix}mediafire
 â€¢ ${prefix}gitclone${petik}

*GROUP MENU*${petik}
 â€¢ ${prefix}afk
 â€¢ ${prefix}welcome
 â€¢ ${prefix}left
 â€¢ ${prefix}pppanjanggc
 â€¢ ${prefix}setopen
 â€¢ ${prefix}changesetopen
 â€¢ ${prefix}delsetopen
 â€¢ ${prefix}setclose
 â€¢ ${prefix}changesetclose
 â€¢ ${prefix}delsetclose
 â€¢ ${prefix}setwelcome
 â€¢ ${prefix}changewelcome
 â€¢ ${prefix}delsetwelcome
 â€¢ ${prefix}setleft
 â€¢ ${prefix}changeleft
 â€¢ ${prefix}delsetleft
 â€¢ ${prefix}linkgc
 â€¢ ${prefix}setppgc
 â€¢ ${prefix}setppgc2 
 â€¢ ${prefix}setnamegc
 â€¢ ${prefix}setdesc
 â€¢ ${prefix}antilink
 â€¢ ${prefix}antiwame
 â€¢ ${prefix}antilink2
 â€¢ ${prefix}antiwame2
 â€¢ ${prefix}open
 â€¢ ${prefix}close
 â€¢ ${prefix}add
 â€¢ ${prefix}kick
 â€¢ ${prefix}promote
 â€¢ ${prefix}demote
 â€¢ ${prefix}revoke
 â€¢ ${prefix}hidetag
 â€¢ ${prefix}checksewa${petik}

*GAME MENU*${petik}
 â€¢ ${prefix}tictactoe
 â€¢ ${prefix}delttt
 â€¢ ${prefix}casino
 â€¢ ${prefix}delcasino${petik}

*SEARCH MENU*${petik}
 â€¢ ${prefix}lirik
 â€¢ ${prefix}grupwa
 â€¢ ${prefix}pinterest
 â€¢ ${prefix}ytsearch${petik}

*RANDOM MENU*${petik}
 â€¢ ${prefix}cecan
 â€¢ ${prefix}cogan
 â€¢ ${prefix}waifu${petik}


*BALANCE MENU*${petik}
 â€¢ ${prefix}topglobal
 â€¢ ${prefix}toplocal
 â€¢ ${prefix}buylimit
 â€¢ ${prefix}buyglimit
 â€¢ ${prefix}transfer
 â€¢ ${prefix}limit
 â€¢ ${prefix}balance${petik}

*STORAGE*${petik}
 â€¢ ${prefix}addstik
 â€¢ ${prefix}addvn
 â€¢ ${prefix}addimg
 â€¢ ${prefix}addvid
 â€¢ ${prefix}liststik
 â€¢ ${prefix}listvn
 â€¢ ${prefix}listimg
 â€¢ ${prefix}listvid${petik}
 
*BAILEYS*${petik}
 â€¢ ${prefix}fitnah
 â€¢ ${prefix}nowa
 â€¢ ${prefix}getquoted
 â€¢ ${prefix}fakehidetag
 â€¢ ${prefix}react
 â€¢ ${prefix}setcmd
 â€¢ ${prefix}delcmd${petik}

*OWNERS MENU*${petik}
 â€¢ ${prefix}autoread
 â€¢ ${prefix}autobio
 â€¢ ${prefix}antidelete
 â€¢ ${prefix}antiviewonce
 â€¢ ${prefix}autorespond
 â€¢ ${prefix}anticall
 â€¢ ${prefix}autoblok212
 â€¢ ${prefix}join
 â€¢ ${prefix}left
 â€¢ ${prefix}self
 â€¢ ${prefix}public
 â€¢ ${prefix}setppbot2
 â€¢ ${prefix}setppbot
 â€¢ ${prefix}broadcast
 â€¢ ${prefix}bcimg
 â€¢ ${prefix}bcstik
 â€¢ ${prefix}bcvn
 â€¢ ${prefix}bcvideo
 â€¢ ${prefix}bcsewa
 â€¢ ${prefix}addpremium
 â€¢ ${prefix}delpremium
 â€¢ ${prefix}addsewa
 â€¢ ${prefix}delsewa${petik}

*ASUPAN MENU*${petik}
 â€¢ ${prefix}chika
 â€¢ ${prefix}delvira
 â€¢ ${prefix}ayu
 â€¢ ${prefix}bunga
 â€¢ ${prefix}aura
 â€¢ ${prefix}nisa
 â€¢ ${prefix}ziva
 â€¢ ${prefix}yana
 â€¢ ${prefix}viona
 â€¢ ${prefix}syania
 â€¢ ${prefix}riri
 â€¢ ${prefix}syifa
 â€¢ ${prefix}mama_gina
 â€¢ ${prefix}alcakenya
 â€¢ ${prefix}mangayutri
 â€¢ ${prefix}rikagusriani
 â€¢ ${prefix}asupan
 â€¢ ${prefix}bocil
 â€¢ ${prefix}geayubi
 â€¢ ${prefix}santuy
 â€¢ ${prefix}ukhty
 â€¢ ${prefix}syifa${petik}

*NSFW MENU*${petik}
 â€¢ ${prefix}baka
 â€¢ ${prefix}smug
 â€¢ ${prefix}neko_sfw
 â€¢ ${prefix}hentai_gif
 â€¢ ${prefix}spank
 â€¢ ${prefix}blowjob
 â€¢ ${prefix}cumarts
 â€¢ ${prefix}eroyuri
 â€¢ ${prefix}eroneko
 â€¢ ${prefix}erokemonomimi
 â€¢ ${prefix}erokitsune
 â€¢ ${prefix}ero
 â€¢ ${prefix}feet
 â€¢ ${prefix}erofeet
 â€¢ ${prefix}feetgif
 â€¢ ${prefix}femdom
 â€¢ ${prefix}futanari
 â€¢ ${prefix}hentai
 â€¢ ${prefix}holoero
 â€¢ ${prefix}holo
 â€¢ ${prefix}keta
 â€¢ ${prefix}kitsune
 â€¢ ${prefix}kemonomimi
 â€¢ ${prefix}pussyart
 â€¢ ${prefix}pussywankgif
 â€¢ ${prefix}girl_solo
 â€¢ ${prefix}girl_solo_gif
 â€¢ ${prefix}tits
 â€¢ ${prefix}trap
 â€¢ ${prefix}yuri
 â€¢ ${prefix}avatar2
 â€¢ ${prefix}anal
 â€¢ ${prefix}bj
 â€¢ ${prefix}boobs
 â€¢ ${prefix}classic
 â€¢ ${prefix}cumsluts
 â€¢ ${prefix}kuni
 â€¢ ${prefix}lesbian
 â€¢ ${prefix}neko
 â€¢ ${prefix}neko_gif
 â€¢ ${prefix}ahegao
 â€¢ ${prefix}bdsm
 â€¢ ${prefix}cuckold
 â€¢ ${prefix}cum
 â€¢ ${prefix}foot
 â€¢ ${prefix}gangbang
 â€¢ ${prefix}glasses
 â€¢ ${prefix}jahy
 â€¢ ${prefix}masturbation
 â€¢ ${prefix}nsfw_neko
 â€¢ ${prefix}orgy
 â€¢ ${prefix}panties
 â€¢ ${prefix}tentacles
 â€¢ ${prefix}thighs
 â€¢ ${prefix}zettai${petik}


*TEXTPRO MENU*${petik}
 â€¢ ${prefix}halloween2
 â€¢ ${prefix}horror
 â€¢ ${prefix}game8bit
 â€¢ ${prefix}layered
 â€¢ ${prefix}glitch2
 â€¢ ${prefix}coolg
 â€¢ ${prefix}coolwg
 â€¢ ${prefix}realistic
 â€¢ ${prefix}space3d
 â€¢ ${prefix}gtiktok
 â€¢ ${prefix}stone
 â€¢ ${prefix}marvel
 â€¢ ${prefix}marvel2
 â€¢ ${prefix}pornhub
 â€¢ ${prefix}avengers
 â€¢ ${prefix}metalr
 â€¢ ${prefix}metalg
 â€¢ ${prefix}metalg2
 â€¢ ${prefix}halloween2
 â€¢ ${prefix}lion
 â€¢ ${prefix}wolf_bw
 â€¢ ${prefix}wolf_g
 â€¢ ${prefix}ninja
 â€¢ ${prefix}3dsteel
 â€¢ ${prefix}horror2
 â€¢ ${prefix}lava
 â€¢ ${prefix}bagel
 â€¢ ${prefix}blackpink
 â€¢ ${prefix}rainbow2
 â€¢ ${prefix}water_pipe
 â€¢ ${prefix}halloween
 â€¢ ${prefix}sketch
 â€¢ ${prefix}sircuit
 â€¢ ${prefix}discovery
 â€¢ ${prefix}metallic2
 â€¢ ${prefix}fiction
 â€¢ ${prefix}demon
 â€¢ ${prefix}transformer
 â€¢ ${prefix}berry
 â€¢ ${prefix}thunder
 â€¢ ${prefix}magma
 â€¢ ${prefix}3dstone
 â€¢ ${prefix}neon
 â€¢ ${prefix}glitch
 â€¢ ${prefix}harry_potter
 â€¢ ${prefix}embossed
 â€¢ ${prefix}broken
 â€¢ ${prefix}papercut
 â€¢ ${prefix}gradient
 â€¢ ${prefix}glossy
 â€¢ ${prefix}watercolor
 â€¢ ${prefix}multicolor
 â€¢ ${prefix}neon_devil
 â€¢ ${prefix}underwater
 â€¢ ${prefix}bear
 â€¢ ${prefix}wonderfulg
 â€¢ ${prefix}christmas
 â€¢ ${prefix}neon_light
 â€¢ ${prefix}snow
 â€¢ ${prefix}cloudsky
 â€¢ ${prefix}luxury2
 â€¢ ${prefix}gradient2
 â€¢ ${prefix}summer
 â€¢ ${prefix}writing
 â€¢ ${prefix}engraved
 â€¢ ${prefix}summery
 â€¢ ${prefix}3dglue
 â€¢ ${prefix}metaldark
 â€¢ ${prefix}neonlight
 â€¢ ${prefix}oscar
 â€¢ ${prefix}minion
 â€¢ ${prefix}holographic
 â€¢ ${prefix}purple
 â€¢ ${prefix}glossyb
 â€¢ ${prefix}deluxe2
 â€¢ ${prefix}glossyc
 â€¢ ${prefix}fabric
 â€¢ ${prefix}neonc
 â€¢ ${prefix}newyear
 â€¢ ${prefix}newyear2
 â€¢ ${prefix}metals
 â€¢ ${prefix}xmas
 â€¢ ${prefix}blood
 â€¢ ${prefix}darkg
 â€¢ ${prefix}joker
 â€¢ ${prefix}wicker
 â€¢ ${prefix}natural
 â€¢ ${prefix}firework
 â€¢ ${prefix}skeleton
 â€¢ ${prefix}balloon
 â€¢ ${prefix}balloon2
 â€¢ ${prefix}balloon3
 â€¢ ${prefix}balloon4
 â€¢ ${prefix}balloon5
 â€¢ ${prefix}balloon6
 â€¢ ${prefix}balloon7
 â€¢ ${prefix}steel
 â€¢ ${prefix}gloss
 â€¢ ${prefix}denim
 â€¢ ${prefix}decorate
 â€¢ ${prefix}decorate2
 â€¢ ${prefix}peridot
 â€¢ ${prefix}rock
 â€¢ ${prefix}glass
 â€¢ ${prefix}glass2
 â€¢ ${prefix}glass3
 â€¢ ${prefix}glass4
 â€¢ ${prefix}glass5
 â€¢ ${prefix}glass6
 â€¢ ${prefix}glass7
 â€¢ ${prefix}glass8
 â€¢ ${prefix}captain_as2
 â€¢ ${prefix}robot
 â€¢ ${prefix}equalizer
 â€¢ ${prefix}toxic
 â€¢ ${prefix}sparkling
 â€¢ ${prefix}sparkling2
 â€¢ ${prefix}sparkling3
 â€¢ ${prefix}sparkling4
 â€¢ ${prefix}sparkling5
 â€¢ ${prefix}sparkling6
 â€¢ ${prefix}sparkling7
 â€¢ ${prefix}decorative
 â€¢ ${prefix}chocolate
 â€¢ ${prefix}strawberry
 â€¢ ${prefix}koifish
 â€¢ ${prefix}bread
 â€¢ ${prefix}matrix
 â€¢ ${prefix}blood2
 â€¢ ${prefix}neonligth2
 â€¢ ${prefix}thunder2
 â€¢ ${prefix}3dbox
 â€¢ ${prefix}neon2
 â€¢ ${prefix}roadw
 â€¢ ${prefix}bokeh
 â€¢ ${prefix}gneon
 â€¢ ${prefix}advanced
 â€¢ ${prefix}dropwater
 â€¢ ${prefix}wall
 â€¢ ${prefix}chrismast
 â€¢ ${prefix}honey
 â€¢ ${prefix}drug
 â€¢ ${prefix}marble
 â€¢ ${prefix}marble2
 â€¢ ${prefix}ice
 â€¢ ${prefix}juice
 â€¢ ${prefix}rusty
 â€¢ ${prefix}abstra
 â€¢ ${prefix}biscuit
 â€¢ ${prefix}wood
 â€¢ ${prefix}scifi
 â€¢ ${prefix}metalr
 â€¢ ${prefix}purpleg
 â€¢ ${prefix}shiny 
 â€¢ ${prefix}jewelry
 â€¢ ${prefix}jewelry2
 â€¢ ${prefix}jewelry3
 â€¢ ${prefix}jewelry4
 â€¢ ${prefix}jewelry5
 â€¢ ${prefix}jewelry6
 â€¢ ${prefix}jewelry7
 â€¢ ${prefix}jewelry8
 â€¢ ${prefix}metalh
 â€¢ ${prefix}golden
 â€¢ ${prefix}glitter
 â€¢ ${prefix}glitter2
 â€¢ ${prefix}glitter3
 â€¢ ${prefix}glitter4
 â€¢ ${prefix}glitter5
 â€¢ ${prefix}glitter6
 â€¢ ${prefix}glitter7
 â€¢ ${prefix}metale
 â€¢ ${prefix}carbon
 â€¢ ${prefix}candy
 â€¢ ${prefix}metalb
 â€¢ ${prefix}gemb
 â€¢ ${prefix}3dchrome
 â€¢ ${prefix}metalb2
 â€¢ ${prefix}metalg
 â€¢ ${prefix}metalg${petik}
`
}

exports.donate = (pushname, ownerNumber) => {
    return`Contact  Owner:
wa.me/${ownerNumber} (Owner)`
}

exports.sewanya = `Untuk List Sewa ubah sendiri di folder command, file help.js ðŸ‘Œ baris ke 521`

KYH - IoT 
Intro till Cloud och Edge Computing


Syftet med detta projekt är att skapa ett enkelt program som kan laddas upp till en ubuntu-server i molnet (AWS). Detta program kommer att 
hantera indata från olika sensorer och lagra denna information i en databas (DynamoDB). Den lagrade informationen kan nås via en webbplats där en tabell 
visar alla information.
Om mottagna data är under en viss nivå utlöses en varning och ett e-postmeddelande skickas till administratören.

All kod skrevs i VS Code och laddas sedan upp till ett arkiv i Github. Sedan klonades förvaret och laddades ner till servern. 
Tanken bakom projektet är att bygga ett markfukt system som kan användas i odlingslådorna under sommaren. I ett andra steg kan systemet anslutas till 
ett automatiskt vattensystem.
I Node Red skapade jag två enkla ingångar. En motsvarar fuktsensorn som skickar data var fjärde timme. Jag skapade också en andra ingång baserad i 
Open Weather API, som rapporterar väderprognosen. Det finns en tredje sensor som rapporterar temperaturen.

Min första idé för projektet var att skicka en varning från AWS som utlöstes av viss övertygelse av värden från sensorerna:
- Luftfuktigheten var lägre än 55%
- Ingen regnprognos
Tyvärr kunde jag inte ställa in ett sådant larm vilket resulterade i bara ett enkelt larm som skickas varje gång luftfuktigheten är lägre än 55%.
Larm sätts upp kring en regel i AWS som sedan använder SNS för att meddela admin via e-post.


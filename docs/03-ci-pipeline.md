# CI pipeline

## What the scripts do

One sentence each for build.sh and test.sh. Test testar att filerna finns. Build säger hur det ska byggas och ska slänga ett felmeddelande om nåt är fel.

## The failure the pipeline caught

What I broke on purpose, and what the pipeline said. A link to the red run is enough. Först runnern startar i en tom mapp, och min kod finns inte där förrän jag hämtar den. Det här är det vanligaste första felet med en pipeline, och nu har du jag har inte lagt till

- name: Check Out the Code
        uses: actions/checkout@v7
till yml filen. Sedan raderade jag en av filerna den ska bygga på.

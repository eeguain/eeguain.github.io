---
---

https://github.com/kimcore/chzzk/tree/main 이용시에

let ChzzkChat;

import('https://cdn.skypack.dev/chzzk').then(module => {
    // Assign the ChzzkChat class to the variable
    ChzzkChat = module.ChzzkChat;
    console.log("ready")

    // Now you can use ChzzkChat anywhere in your code where ChzzkChat is in scope
});

const client = new ChzzkChat({
    chatChannelId: "N15cWS",
    accessToken: "OfCpo3LBLFO/5VffnIeGSppagyl7V3fHzVnlgfVINvTePVPAHSQm1KwctdlPL+b2"
})

client.on('chat', chat => {
    const message = chat.hidden ? "[블라인드 처리 됨]" : chat.message
    console.log(`${chat.profile.nickname}: ${message}`)

    // 유저의 팔로우 일시 불러오기
    // client.chat.profileCard(chzzkChat.chatChannelId, chat.profile.userIdHash).then(profile => {
    //     const following = profile.streamingProperty.following
    //     console.log(following ? `${following.followDate} 에 팔로우 함` : "팔로우 안함")
    // })
})

await client.connect()

끌때는 client.disconnect()


이용안하고 독립적으로

const serverId = Math.abs(
    "N15cWS".split("")
        .map(c => c.charCodeAt(0))
        .reduce((a, b) => a + b)
) % 9 + 1;

const ws = new WebSocket(`wss://kr-ss${serverId}.chat.naver.com/chat`);

ws.onopen = () => {
    console.log(111111111);

    // Send the initial message here, after the connection is open
    ws.send(JSON.stringify({
        bdy: {
            accTkn: "6IMUqnFQJ13ZJlIXBTdVeCj/CWppc22hsCoibsa5HxbNd1GXcz5Mz6a57EX8Yi74",
            auth: "READ",
            devType: 2001
        },
        cmd: 100,
        tid: 1,
        cid: "N15cWS",
        svcid: "game",
        ver: "2"
    }));
};

ws.onmessage = (m) => { console.log(JSON.parse(m.data)); };


url에서 복사해서 붙여넣기하고
버튼 누르면
닉네임: 메세지 
이거 나오게 하는 것까지.
그 다음은 거기에 연동해서 캔버스에 그리기.

pve

pvp
url 두 개 붙여넣기하고 대결 시작하면
캔버스에 전투 보임.


chatchannelid token 받아오려면 cors에서 막히는듯
프록시 서버를 만들면 해결
혹시 브라우저 안에서 node.js를 돌리는건? webcontainer같은걸로 그리고 puppet같은걸 거기서 돌리면 cors 문제 없이 되려나? 여전히 cors 에러 뜨려나? 긁어온 다음에 js로 넘기는 건 되려나?


afreecatv의 경우는 아래 참조
https://cha2hyun.blog/content/projects/%EB%B0%B0%EB%8F%8C%EC%9D%B4%EC%9D%98%EB%8B%B9%EA%B5%AC%EC%83%9D%ED%99%9C/afreecatv-crawling/
모바일 버전에서 afreecatv에 들어가서 console network를 보면 websocket 2개가 연결된 것이 보임.

youtube live의 경우는 공식 api를 쓰면
한 번 불러 올 때 5개의 quota를 씀. 하루에 10,000개의 quota 받을 수 있음.


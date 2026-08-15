<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>NIJUN & YONGYI</title>

<style>

* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    background: #f8f6f2;
    color: #333;
    font-family: Georgia, "Noto Serif TC", serif;
}

/* ===== 開場 ===== */

.cover {
    height: 100vh;
    min-height: 650px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 30px;
}

.cover-content {
    max-width: 700px;
}

.small-title {
    font-size: 12px;
    letter-spacing: 4px;
    margin-bottom: 28px;
}

.names {
    font-size: clamp(42px, 10vw, 76px);
    font-weight: normal;
    letter-spacing: 5px;
    margin: 0;
}

.date {
    font-size: 15px;
    letter-spacing: 5px;
}

.divider {
    width: 45px;
    height: 1px;
    background: #999;
    margin: 30px auto;
}

.open-button {
    display: inline-block;
    padding: 13px 32px;
    border: 1px solid #777;
    color: #333;
    text-decoration: none;
    font-size: 11px;
    letter-spacing: 3px;
    transition: 0.3s;
}

.open-button:hover {
    background: #333;
    color: white;
}

/* ===== 正式喜帖 ===== */

.section {
    padding: 100px 25px;
    text-align: center;
    max-width: 850px;
    margin: auto;
}

.section h2 {
    font-size: 28px;
    font-weight: normal;
    letter-spacing: 4px;
}

.section p {
    line-height: 2;
    font-size: 15px;
}

/* ===== 音樂 ===== */

.music-button {
    position: fixed;
    right: 20px;
    bottom: 20px;
    width: 48px;
    height: 48px;
    border-radius: 50%;
    border: 1px solid #777;
    background: rgba(248,246,242,0.9);
    cursor: pointer;
    font-size: 18px;
    z-index: 1000;
}

/* ===== 婚禮資訊 ===== */

.info {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
    margin-top: 45px;
}

.info-box {
    padding: 35px 20px;
    border-top: 1px solid #bbb;
    border-bottom: 1px solid #bbb;
}

.info-title {
    font-size: 12px;
    letter-spacing: 3px;
    margin-bottom: 15px;
}

.info-text {
    font-size: 16px;
    line-height: 1.8;
}

/* ===== RSVP ===== */

.rsvp-button {
    display: inline-block;
    margin-top: 30px;
    padding: 15px 38px;
    background: #333;
    color: white;
    text-decoration: none;
    letter-spacing: 3px;
    font-size: 12px;
}

/* ===== 手機版 ===== */

@media (max-width: 600px) {

    .names {
        font-size: 43px;
    }

    .info {
        grid-template-columns: 1fr;
    }

    .section {
        padding: 80px 25px;
    }

}

</style>
</head>


<body>


<!-- =========================
     開場
========================= -->

<section class="cover">

    <div class="cover-content">

        <div class="small-title">
            WE ARE GETTING MARRIED
        </div>

        <h1 class="names">
            NIJUN & YONGYI
        </h1>

        <div class="divider"></div>

        <div class="date">
            20 DECEMBER 2026
        </div>

        <div class="divider"></div>

        <a href="#invitation" class="open-button" onclick="startMusic()">
            OPEN INVITATION
        </a>

    </div>

</section>


<!-- =========================
     背景音樂
========================= -->

<audio id="bgMusic" loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<button class="music-button" onclick="toggleMusic()">
    ♫
</button>


<!-- =========================
     正式喜帖
========================= -->

<section class="section" id="invitation">

    <h2>OUR STORY</h2>

    <div class="divider"></div>

    <p>

        Our story is just beginning.

        <br><br>

        We would love to share
        this special day with you.

    </p>

</section>


<!-- =========================
     婚禮資訊
========================= -->

<section class="section">

    <h2>THE WEDDING DAY</h2>

    <div class="divider"></div>


    <div class="info">

        <div class="info-box">

            <div class="info-title">
                DATE
            </div>

            <div class="info-text">
                20 DECEMBER 2026
            </div>

        </div>


        <div class="info-box">

            <div class="info-title">
                TIME
            </div>

            <div class="info-text">
                XX : XX
            </div>

        </div>


        <div class="info-box">

            <div class="info-title">
                CEREMONY
            </div>

            <div class="info-text">
                XX : XX
            </div>

        </div>


        <div class="info-box">

            <div class="info-title">
                RECEPTION
            </div>

            <div class="info-text">
                XX : XX
            </div>

        </div>

    </div>

</section>


<!-- =========================
     RSVP
========================= -->

<section class="section">

    <h2>WILL YOU JOIN US?</h2>

    <div class="divider"></div>

    <p>

        We would love to celebrate
        this special day with you.

    </p>


    <!-- 之後把下面網址換成你的 RSVP 表單 -->

    <a
        href="https://forms.google.com/"
        target="_blank"
        class="rsvp-button">

        RSVP

    </a>

</section>


<!-- =========================
     結尾
========================= -->

<section class="section">

    <h2>THANK YOU</h2>

    <div class="divider"></div>

    <p>

        Thank you for being part of
        our story and our special day.

        <br><br>

        NIJUN & YONGYI

    </p>

</section>


<script>

const music = document.getElementById("bgMusic");

function startMusic() {

    music.play().catch(function() {
        console.log("Music playback requires user interaction.");
    });

}

function toggleMusic() {

    if (music.paused) {

        music.play();

    } else {

        music.pause();

    }

}

</script>


</body>
</html>

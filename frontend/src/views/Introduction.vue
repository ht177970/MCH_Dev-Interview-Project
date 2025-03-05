<template>
  <div class="introduction">
    <header class="intro-header">
      <div class="profile-container">
        <div class="profile-image-container">
          <img src="/me.png" alt="曾彥熹" class="profile-image" />
        </div>
        <div class="intro-text">
          <h2>曾彥熹</h2>
          <p>
            交大資工二年級，從高一開始打競程至今仍未放棄，除了競程之外陸陸續續有一點小作品，但都是單人完成，因此作品規模相對小。我認為我自己是小E人，在團隊中應屬於那種做事時進入認真模式，休息時很吵鬧的一個人，相信我能夠與團隊相處融洽，希望能夠加入黑克松這個團隊與大家一起學習和開發專案！
          </p>
        </div>
      </div>
    </header>

    <section class="about-section">
      <h3>程式語言技能</h3>
      <ul>
        <li v-for="skill in skills" :key="skill">{{ skill }}</li>
      </ul>
      <h3>小作品</h3>
      <ul>
        <li v-for="project in projects" :key="project.name">
          <strong>{{ project.name }}</strong>: {{ project.description }}
          <a v-if="project.link" :href="project.link" target="_blank" rel="noopener noreferrer">(更多資訊)</a>
        </li>
      </ul>
      <h3>得獎紀錄</h3>
      <ul>
        <li v-for="award in awards" :key="award">{{ award }}</li>
      </ul>
    </section>
  </div>
</template>

<script setup>
const awards = [
  "2023 ICPC Asia Taoyuan Regional Programming Contest 銅牌獎",
  "113年度交大程式設計競賽個人賽 佳作(第五名)",
  "113年度交大程式設計新生賽 壹等獎",
  "111學年度臺北市資訊科能力競賽 三等獎",
  "110學年度臺北市資訊科能力競賽 佳作",
  "111學年度中正高中資訊科能力競賽 第一名",
  "110學年度中正高中資訊科能力競賽 第一名",
  "109學年度中正高中資訊科能力競賽 第三名",
  "2023 Math Kangaroo Taiwan 袋鼠數學比賽 金牌獎",
  "2022 Meta Hacker Cup TOP2000",
  "TOI第七屆新手同好會團體賽 第一名",
  "TOI第六屆新手同好會團體賽 第一名",
];

const projects = [
  { name: "Discord bot", description: "國中用C#撰寫，用來管理訊息與播放音訊等趣味功能。" },
  { name: "Anti-Unsent", description: "高一用Python+Java撰寫，設計包含PC端(Server)與Android端(Client)，利用Python爬蟲、Java與手機端更新資料。", link: "Anti-Unsent.pdf" },
  { name: "Snake", description: "高二用C++撰寫，主要練習物件導向寫法與SFML框架使用，單人貪食蛇遊戲。", link: "https://github.com/ht177970/ForSchool_Snake_v2" },
  { name: "RyanPlatformer", description: "高三用C++撰寫，主要練習物件導向寫法與SFML框架使用，單人跑酷遊戲。", link: "https://github.com/ht177970/RyanPlatformer" },
  { name: "TimeLapseRecorder", description: "高三用C#撰寫，為了錄製縮時而製作。" },
  { name: "四人將棋", description: "大一用React撰寫前端，Python+Sonic撰寫後端伺服器，是基於高中同學寫的Vue改寫而來並做後續更新。", link: "Shogi" },
  { name: "RunTogether", description: "大二用C++撰寫，基於高三的作品改成多人連線版，從Windows平台轉至Linux，多人競速跑酷遊戲。", link: "https://github.com/ht177970/RunTogeter" },
];

const skills = ["C/C++/C#", "Java", "Python", "React"];
</script>

<style scoped>
.introduction {
  padding: 40px 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.intro-header {
  background-color: #f5f5f5;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.profile-container {
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

.profile-image-container {
  width: 150px;
  height: 150px;
  margin-right: 20px;
  border-radius: 50%;
  overflow: hidden;
  border: 5px solid #ddd;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  transition: transform 0.3s ease-in-out;
}

.profile-image:hover {
  transform: scale(1.1);
}

.intro-text {
  flex-grow: 1;
}

.intro-text h2 {
  font-size: 2rem;
  margin-bottom: 10px;
}

.intro-text p {
  font-size: 1.1rem;
  color: #333;
  margin-bottom: 20px;
  line-height: 1.6;
}

.about-section {
  margin-top: 40px;
  padding: 0 40px;
}

.about-section h3 {
  font-size: 1.6rem;
  margin-top: 20px;
  margin-bottom: 10px;
  position: relative;
}

.about-section h3::after {
  content: '';
  display: block;
  width: 50px;
  height: 3px;
  background: #007bff;
  margin-top: 5px;
}

.about-section ul {
  list-style-type: none;
  padding: 0;
}

.about-section li {
  font-size: 1rem;
  line-height: 1.6;
  padding: 5px 0;
  transition: transform 0.2s ease-in-out;
}

.about-section li:hover {
  transform: translateX(5px);
  color: #ffc23d;
}
</style>

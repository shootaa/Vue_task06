<template>
  <div id="app">
    <div class="container">
      <div class="card" v-for="(company, index) in companies" :key="index">
        <h2>{{ company.name }}</h2>

        <div class="card-content">
          <div class="card-employee">
            <span>{{ company.employee.position }}</span>
            <h1>{{ company.employee.englishName }}</h1>
            <span>{{ company.employee.japaneseName }}</span>
          </div>

          <footer class="card-company">
            <span>{{ company.fullName }}</span>
            <span>{{ company.zipCode }}</span>
            <span>{{ company.address }}</span>
            <span>{{ company.addressExtended }}</span>
            <span>
              MAIL
              <span>{{ company.employee.email }}</span>
            </span>
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      companies: [
        {
          name: "LABOT",
          fullName: "株式会社LABOT",
          zipCode: "〒150 - 6090",
          address: "東京都渋谷区恵比寿4-20-4",
          addressExtended: "恵比寿ガーデンプレイスグラススクエアB1",
          employee: {
            position: "Engineer",
            englishName: "Ryosuke Takahashi",
            japaneseName: "高橋涼介",
            email: "takahashi@labot.inc"
          }
        },
        {
          name: "LABOT",
          fullName: "株式会社LABOT",
          zipCode: "〒150 - 6090",
          address: "東京都渋谷区恵比寿4-20-4",
          addressExtended: "恵比寿ガーデンプレイスグラススクエアB1",
          employee: {
            position: "Engineer",
            englishName: "Takumi Fujiwara",
            japaneseName: "藤原拓海",
            email: "fujiwara@labot.inc"
          }
        }
      ]
    };
  }
};
</script>

<style lang="scss">
$bg: #fceeb5;
$border: #dcdcdc;

body {
  background-color: $bg;
  margin: 0 auto;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 15px;
}

.container {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.card {
  background-color: #ffffff;
  border: 1px solid $border;
  min-width: 500px;
  max-width: 500px;
  min-height: 270px;
  padding: 30px;
  display: flex;
  justify-content: flex-end;
  flex-wrap: wrap;
  margin: 15px 0;

  h2 {
    margin: 0;
    width: 100%;
  }

  .card-employee {
    margin-bottom: 30px;
    span {
      &:first-of-type {
        font-weight: bold;
      }

      &:last-of-type {
        opacity: 0.7;
      }
    }

    h1 {
      margin: 5px 0;
    }
  }

  .card-company {
    font-weight: 500;
    display: flex;
    flex-direction: column;

    span {
      font-size: 14px;
      &:first-of-type {
        font-size: 15px;
      }

      &:nth-of-type(2) {
        font-size: 12px;
      }

      & > span {
        font-weight: bold;
      }
    }
  }
}
</style>

<template>
    <div>
      <div class="reg">
        <input type="number" maxlength="3" v-model="inCode"/>
        <div class="rus">
          RUS
          <img class="flag" :src="rusFlag"/>
        </div>
      </div>
      <div class="result" v-if="selected && selected.length">
          <div v-for="(code, index) in selected" :key="index" class="result-item">
            {{code.region}}
            <div class="muted">
              <span v-for="c in code.code" :key="c">{{c}}&nbsp;</span>
            </div>
          </div>
      </div>
      <div v-else class="result muted">
          Ничего не найдено
      </div>
    </div>
</template>

<script>
export default {
  name: "RoadNum",
  computed: {
    selected() {
      if (this.inCode && this.inCode.length > 0) {
        return this.codes.filter(item => {
          return item.code.some((el) => {
            return el.indexOf(this.inCode) >= 0;
          });
        });
      } else return [];
    }
  },
  data: function() {
    return {
      rusFlag: require("@/assets/russia-flag-icon-32.png"),
      inCode: "",
      codes: [
        { region: "Республика Адыгея", code: ["01", "101"] },
        { region: "Республика Башкортостан", code: ["02", "102"] },
        { region: "Республика Бурятия", code: ["03", "103"] },
        { region: "Республика Алтай", code: ["04"] },
        { region: "Республика Дагестан", code: ["05"] },
        { region: "Республика Ингушетия", code: ["06"] },
        { region: "Кабардино-Балкарская Республика", code: ["07"] },
        { region: "Республика Калмыкия", code: ["08"] },
        { region: "Карачаево-Черкесская Республика", code: ["09", "109"] },
        { region: "Республика Карелия", code: ["10"] },
        { region: "Республика Коми", code: ["11"] },
        { region: "Республика Марий Эл", code: ["12"] },
        { region: "Республика Мордовия", code: ["13", "113"] },
        { region: "Республика Саха (Якутия)", code: ["14"] },
        { region: "Республика Северная Осетия-Алания", code: ["15"] },
        { region: "Республика Татарстан", code: ["16", "116"] },
        { region: "Республика Тыва", code: ["17"] },
        { region: "Удмуртская Республика", code: ["18", "118"] },
        { region: "Республика Хакасия", code: ["19"] },
        { region: "Чеченская республика", code: ["20", "95"] },
        { region: "Чувашская Республика", code: ["21", "121"] },
        { region: "Алтайский край", code: ["22"] },
        { region: "Краснодарский край", code: ["23", "93", "123"] },
        { region: "Красноярский край", code: ["24", "84", "88", "124"] },
        { region: "Приморский край", code: ["25", "125"] },
        { region: "Ставропольский край", code: ["26"] },
        { region: "Хабаровский край", code: ["27"] },
        { region: "Амурская область", code: ["28"] },
        { region: "Архангельская область", code: ["29"] },
        { region: "Астраханская область", code: ["30"] },
        { region: "Белгородская область", code: ["31"] },
        { region: "Брянская область", code: ["32"] },
        { region: "Владимирская область", code: ["33"] },
        { region: "Волгоградская область", code: ["34", "134"] },
        { region: "Вологодская область", code: ["35"] },
        { region: "Воронежская область", code: ["36", "136"] },
        { region: "Ивановская область", code: ["37"] },
        { region: "Иркутская область", code: ["38", "85", "138"] },
        { region: "Калининградская область", code: ["39", "91"] },
        { region: "Калужская область", code: ["40"] },
        { region: "Камчатский край", code: ["41"] },
        { region: "Кемеровская область", code: ["42", "142"] },
        { region: "Кировская область", code: ["43"] },
        { region: "Костромская область", code: ["44"] },
        { region: "Курганская область", code: ["45"] },
        { region: "Курская область", code: ["46"] },
        { region: "Ленинградская область", code: ["47"] },
        { region: "Липецкая область", code: ["48"] },
        { region: "Магаданская область", code: ["49"] },
        {
          region: "Московская область",
          code: ["50", "90", "150", "190", "750"]
        },
        { region: "Мурманская область", code: ["51"] },
        { region: "Нижегородская область", code: ["52", "152"] },
        { region: "Новгородская область", code: ["53"] },
        { region: "Новосибирская область", code: ["54", "154"] },
        { region: "Омская область", code: ["55"] },
        { region: "Оренбургская область", code: ["56"] },
        { region: "Орловская область", code: ["57"] },
        { region: "Пензенская область", code: ["58"] },
        { region: "Пермский край", code: ["59", "81", "159"] },
        { region: "Псковская область", code: ["60"] },
        { region: "Ростовская область", code: ["61", "161"] },
        { region: "Рязанская область", code: ["62"] },
        { region: "Самарская область", code: ["63", "163"] },
        { region: "Саратовская область", code: ["64", "164"] },
        { region: "Сахалинская область", code: ["65"] },
        { region: "Свердловская область", code: ["66", "96", "196"] },
        { region: "Смоленская область", code: ["67"] },
        { region: "Тамбовская область", code: ["68"] },
        { region: "Тверская область", code: ["69"] },
        { region: "Томская область", code: ["70"] },
        { region: "Тульская область", code: ["71"] },
        { region: "Тюменская область", code: ["72"] },
        { region: "Ульяновская область", code: ["73", "173"] },
        { region: "Челябинская область", code: ["74", "174"] },
        { region: "Забайкальский край", code: ["75", "80"] },
        { region: "Ярославская область", code: ["76"] },
        {
          region: "Москва",
          code: ["77", "97", "99", "177", "197", "199", "777"]
        },
        { region: "Санкт-Петербург", code: ["78", "98", "178"] },
        { region: "Еврейская автономная область", code: ["79"] },
        { region: "Республика Крым", code: ["82"] },
        { region: "Ненецкий АО", code: ["83"] },
        { region: "Ханты-Мансийский АО", code: ["86", "186"] },
        { region: "Чукотский АО", code: ["87"] },
        { region: "Ямало-Ненецкий АО", code: ["89"] },
        { region: "Севастополь", code: ["92"] },
        { region: "Байконур", code: ["94"] }
      ]
    };
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Marmelad");
@font-face {
  font-family: RoadFont;
  src: url("../assets/RoadNumbers.otf");
}

.reg {
  margin: 0 auto;
  width: 200px;
  border: 5px solid black;
  padding: 5px;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
}

.reg > input {
  border: 0;
  cursor: pointer;
  height: 100px;
  text-align: center;
  font-family: "RoadFont";
  font-size: 90pt;
  width: 190px;
}

.rus {
  font-size: 26pt;
  font-family: sans-serif;
  text-align: center;
}

.flag {
  border: 1px solid black;
}

.result {
  margin-top: 20px;
  text-align: center;
  font-family: "Marmelad", sans-serif;
  font-size: 16pt;
}

.muted {
  color: darkgray;
}
</style>
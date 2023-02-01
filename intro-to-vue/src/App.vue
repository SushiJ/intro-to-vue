<script>
import CharacterCard from './components/CharacterCard.vue'
import FavoriteList from './components/FavoriteList.vue'
export default {
  components: {
    CharacterCard,
    FavoriteList
  },
  data: () => ({
    characterList: [
      {
        name: "Jinx",
        image: "https://static.wikia.nocookie.net/leagueoflegends/images/9/90/Jinx_Arcane_6_Render.png"
      },
      {
        name: "Vi",
        image: "https://static.wikia.nocookie.net/leagueoflegends/images/8/85/Vi_Arcane_4_Render.png"
      },
      {
        name: "Ekko",
        image: "https://static.wikia.nocookie.net/leagueoflegends/images/d/de/Ekko_Arcane_4_Render.png"
      },
      {
        name: "Caitlyn",
        image: "https://static.wikia.nocookie.net/leagueoflegends/images/0/04/Caitlyn_Arcane_6_Render.png"
      },
      {
        name: "Viktor",
        image: "https://static.wikia.nocookie.net/leagueoflegends/images/3/33/Viktor_Arcane_2_Render.png"
      },
    ],
    favoriteCharacterList: [],
  }),
  methods: {
    removeFavorite(payload) {
      this.favoriteCharacterList = this.favoriteCharacterList.filter(char => char.name != payload.name)
    },
    addFavorite(payload) {
      if (this.favoriteCharacterList.includes(payload)) {
        return
      }
      this.favoriteCharacterList.push(payload)
    }
  }
}
</script>

<template>
  <div class="bg-zinc-800 text-zinc-50 h-screen">
    <div id="app" class="h-full">
      <p v-if="characterList.length === 0">
        <img src="https://cdn3.emoji.gg/emojis/5960_NotLikeThis.png" alt="NotLikeThis Twitch Emote">
      </p>
      <div class="flex justify-center items-center h-full flex-col">
        <div class="flex gap-4">
          <div v-for="character in characterList" class="">
            <CharacterCard :character="character" @favorite="addFavorite" />
          </div>
        </div>
        <div class="mt-4 text-lg">
          <p v-if="favoriteCharacterList.length === 0">No Favorites</p>
          <ul class="flex">
            <li v-for="favoriteCharacter in favoriteCharacterList">
              <FavoriteList :favoriteCharacter="favoriteCharacter" @removeFavorite="removeFavorite" />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

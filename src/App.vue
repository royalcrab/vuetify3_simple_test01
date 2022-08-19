<template>
  <v-app id="mplpl" theme="mplpl">
    <v-navigation-drawer
      v-model="drawer"
    >
    <!-- permanent で常設になる -->
    <!-- app bar より下に書くと、app-var より下に描画される -->
    <!-- v-model="drawer" を書くと、ボタンを押すとポップアップする -->
      <v-list-item>
          <v-list-item-title class="text-h6">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        density="compact"
        nav
      >
        <v-list-item prepend-icon="mdi-view-dashboard" title="Home" value="home"></v-list-item>
        <v-list-item prepend-icon="mdi-forum" title="About" value="about"></v-list-item>
      </v-list>

    </v-navigation-drawer>

    <!-- app 属性をつけることで、app の一部としてパーツ分のマージンが取られる。-->
    <v-app-bar app
      color="primary"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>

      <v-btn
        id="menu-activator"
      >
        めにゅう
      </v-btn>

      <v-menu activator="#menu-activator">
        <v-list>
          <v-list-item
            v-for="(item, index) in menu"
            :key="index"
            :value="index"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn>
        <v-icon>
          mdi-home
        </v-icon>
      </v-btn>
    </v-app-bar>



<!-- v-main の中にコンテンツを置くこと。
         サイドバーやメニューの大きさが変わったときにでも自動的にリサイズされる -->
    <v-main>
      <v-container>
        <v-btn>
          ほげ1
        </v-btn>
        <v-btn>
          ほげ2
        </v-btn>
        <v-btn>
          ほげ3
        </v-btn>
      </v-container>

      <v-container>
        <div class="d-flex"> <!-- d-flex で均等割り付け -->
        <v-btn>
          ほげ1
        </v-btn>
        <v-btn>
          ほげ2
        </v-btn>
        <v-btn>
          ほげ3
        </v-btn>
        </div>
      </v-container>

      <v-container>
        <div class="d-flex justify-space-around"> <!-- d-flex で均等割り付け -->
        <v-btn color="primary">
          ほげ1
        </v-btn>
        <v-btn color="secondary">
          ほげ2
        </v-btn>
        <v-btn color="error">
          ほげ3
        </v-btn>
        </div>
      </v-container>

      <v-container>
        <div class="d-flex"> <!-- d-flex で均等割り付け -->
          <v-sheet v-for="n in [1,2,3,4,5]"
            :key="n" class="pa-1 ma-1" color="secondary">
            <v-btn class="ma-5">
              ほげ{{n}}
            </v-btn>
          </v-sheet>
        </div>
      </v-container>

      <v-container>
        <div class="d-flex"> <!-- d-flex で均等割り付け -->
          <v-btn v-for="n in [1,2,3,4,5]"
            :key="n" class="pa-5 ma-5" color="secondary" height="5em">
              ほげ{{n}}
          </v-btn>
        </div>
      </v-container>

      <!-- v-container はデフォルトで左右にマージンが設定されている -->
      <v-container>
        <v-row>
        <v-col>
          <v-sheet
            color="grey lighten-3"
            height="10em"
            
          >
            ほげ1
          </v-sheet>
        </v-col>
        <v-col>
          <v-sheet
            color="grey lighten-3"
            height="10em"
            
          >
            ほげ2
          </v-sheet>
        </v-col>
        <v-col>
          <v-sheet
            color="grey lighten-3"
            height="10em"
            
          >
            ほげ3
          </v-sheet>
        </v-col>
      </v-row>
      </v-container>
      <v-container>
        <v-row>
          <v-col cols="3" v-for="(item, id) in hogex" :key="id">
            <v-sheet
              color="secondary"
              height="5em"
            >
              {{item.name}}
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>

      <v-container>
        <v-row>
          <v-col cols="8">
            <v-sheet color="grey lighten-3" height="21em">
              ほげ1
            </v-sheet>
          </v-col>

          <v-col cols="4">
            <v-row>
              <v-col>
                <v-sheet color="grey lighten-3" height="10em">
                  ほげ2
                </v-sheet>
              </v-col>
            </v-row>

            <v-row>
              <v-col>
                <v-sheet color="grey lighten-3" height="10em">
                  ほげ3
                </v-sheet>
              </v-col>
            </v-row>

          </v-col>
        </v-row>

      </v-container>

      <v-container>
        <v-row>
          <v-col>
            <v-btn height="5em" width="10em">
              ほげ1
            </v-btn>
          </v-col>

          <v-col>
            <v-btn height="5em">
              ほげ2
            </v-btn>
          </v-col>
 
           <v-col>
            <v-btn height="5em">
              ほげ3
            </v-btn>
          </v-col>

          <v-col>
            <v-btn height="5em">
              ほげ4
            </v-btn>
          </v-col>

          <v-col>
            <v-btn height="5em">
              ほげ5
            </v-btn>
          </v-col>

          <v-col>
            <v-btn height="5em">
              ほげ6
            </v-btn>
          </v-col>

        </v-row>
      </v-container>

    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => (
    {
      drawer: null,
      items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard' },
        { title: 'Photos', icon: 'mdi-image' },
        { title: 'About', icon: 'mdi-help-box' },
      ],
      right: null,
      hogex: [
        { name: "1" },
        { name: "2" },
        { name: "3" },
        { name: "4" },
        { name: "5" },
        { name: "6" },
        { name: "7" },
        { name: "8" },
        { name: "9" },
        { name: "10" },
        { name: "11" },
        { name: "12" },
        { name: "13" },
        { name: "14" },
        { name: "15" },
      ],
      menu: [
        { title: 'Click Me1' },
        { title: 'Click Me2' },
        { title: 'Click Me3' },
        { title: 'Click Me4' },
      ],
    }
  ),
}
</script>

<template>
    <div class="home">
        <div class="center">
            <card>
              <template #title>
                申请 Seati 白名单
              </template>
              <template #content>
                <p><strong>Seati</strong> 是 Oasis 旗下的模组服务器。在这里你可以体验到</p>
                <ul>
                  <li>有别于其它服务器的轻松游戏氛围</li>
                  <li>和管理团队零距离接触</li>
                  <li>提出自己喜爱的模组搭配并通过投票选出周目的模组主题</li>
                </ul>
                <p>若要获取 Seati 的白名单，你需要完成这个简单的问卷并通过审核。整个流程大概消耗 10~15 分钟。</p>
                <quiz>
                  <template #number>1</template>
                  <template #title>你的 Minecraft 游戏名称是？</template>
                  <template #desc>填写你的 Minecraft Java 版游戏名称。请填写完整，注意下划线的数量和大小写。</template>
                  <template #content>
                    <textfield v-model="states.formdata.playername"/>
                  </template>
                </quiz>
                <quiz>
                  <template #number>2</template>
                  <template #title>你的联系方式是？</template>
                  <template #desc>请提供至少一种联系方式以便我们可以及时通知你一些重要的信息（如有必要）。建议提供不涉及个人隐私的常用联系方式。</template>
                  <template #content>
                    <textfield v-model="states.formdata.playername"/>
                  </template>
                </quiz>
              </template>
              <template #action>
                <r to="/apply">
                   开始填写
                </r>
              </template>
            </card>
        </div>
    </div>
</template>

<script setup lang="ts">
import Card from '@/components/Card.vue'
import Quiz from "@/components/Quiz.vue";
import Textfield from "@/components/Textfield.vue";
import states from "@/states";
import R from "@/components/R.vue";
</script>

<style lang="less">
.center {
    display: flex;
    width: 100vw;
    height: 100vh;
    align-items: center;
    justify-content: center;
}
</style>
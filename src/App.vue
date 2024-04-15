<script setup lang="ts">
import Dropdown from "./components/Dropdown.vue";
import Modal from "./components/Modal.vue";
import { ref } from "vue";

const isModalOpen = ref(false);
</script>

<template>
  <div class="">
    <div class="yl flex justify-center items-center w-svw h-dvh">
      <div class="flex flex-col gap-4">
        <button @click="isModalOpen = true">modal bez tlacitka - TOP</button>

        <!-- modal bez tlacitka -->
        <Modal v-model="isModalOpen" position="top" :showButton="false">
          <template #content>modal bez tlacitka</template>
        </Modal>

        <!-- modal fullscreen -->
        <Modal position="fullscreen">
          <template #button>modal s tlacitkem - fullscreen</template>
          <template #content>
            <div class="overflow-auto max-h-full p-12">
              <div>
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ex
                quibusdam dolorem at? Libero nisi et nihil. Nobis porro sint
                magni possimus quisquam accusamus voluptas quos? Unde commodi
                ratione maiores voluptas?
              </div>
              <div>
                Optio nulla nam provident veritatis voluptatem nihil at nemo
                corrupti, dolore obcaecati doloribus sed suscipit ipsa ipsum
                ullam vero sint, perspiciatis non repellat totam aliquam illum
                ducimus impedit. Esse, culpa.
              </div>
              <div>
                Autem, placeat hic. Sunt quidem nemo aliquam dolorem blanditiis
                nesciunt voluptatum omnis? Magnam modi tenetur numquam at
                fugiat, nostrum nihil sit exercitationem dolores obcaecati
                voluptas iusto qui a quidem in?
              </div>
              <div>
                Architecto animi laudantium suscipit iusto voluptas incidunt
                accusantium repudiandae, quis itaque vel? Culpa, eos nobis
                excepturi minima nesciunt velit, ex voluptate recusandae quae
                accusantium odio itaque vel cum perspiciatis iste.
              </div>
              <div>
                Nulla accusantium unde possimus, pariatur atque omnis animi id
                vero neque quidem nihil ipsum natus delectus veniam, velit
                explicabo. Nulla ut vitae ipsa. Sint fugit architecto ullam
                vero, quod a.
              </div>
              <div>
                Nisi repellendus pariatur corrupti laudantium dolorem
                perspiciatis voluptate, placeat ullam, molestias praesentium
                nihil similique totam provident dolorum incidunt in possimus vel
                suscipit accusamus a ea sed voluptatem? Repellendus, tempore
                harum.
              </div>
              <div>
                Eum aspernatur dolor labore laudantium modi natus facilis
                aliquam, nemo error corporis asperiores saepe id, quasi deleniti
                illo accusantium iure ducimus dolores! Soluta adipisci minus
                quia eligendi perferendis amet assumenda!
              </div>
              <div>
                Voluptas, molestiae vitae suscipit earum deserunt a, consequatur
                temporibus eveniet odio aut ut quam soluta, nam omnis ullam.
                Minima repellat sed fuga quibusdam porro vero impedit, rem
                voluptatibus accusantium maxime.
              </div>
              <div>
                Laborum, enim sit modi quis quidem omnis quasi reprehenderit
                tenetur quos dicta rem laudantium dolore placeat accusantium
                eius iusto praesentium accusamus voluptatem reiciendis aliquam
                possimus. Porro impedit voluptatem et assumenda.
              </div>
              <div>
                Repellendus aperiam quae voluptate cupiditate hic, rem quas
                neque facilis libero quis laudantium non facere distinctio autem
                quaerat esse dignissimos voluptas cum, ea reprehenderit, veniam
                deleniti maiores adipisci laboriosam! Ad.
              </div>
              <div>
                Nisi sint, eos aperiam harum necessitatibus officiis, quia
                suscipit maxime incidunt ad reiciendis rem praesentium dolore
                iste deserunt? Iure alias eaque sunt, similique harum rerum
                ducimus beatae rem. Illum, vitae.
              </div>
              <div>
                Quia aperiam recusandae quos distinctio maxime non laudantium
                voluptate illum, accusamus magni in sunt numquam, molestiae at
                commodi illo vero quas tempore repudiandae exercitationem nihil,
                porro incidunt quis est. In.
              </div>
              <div>
                Nesciunt fugiat harum, repellendus fugit dolores, cupiditate a
                tempore commodi deserunt doloribus numquam quaerat quod
                quibusdam nisi provident molestias voluptatibus. Quod assumenda
                qui exercitationem ab illum maiores laboriosam corrupti fugit!
              </div>
              <div>
                Vero nihil cum ullam deserunt veniam maxime velit totam in eos,
                eum soluta quos laborum accusamus sit, illum labore aliquid nemo
                adipisci repellendus eligendi dolores fugit! Atque harum aperiam
                minus!
              </div>
              <div>
                Obcaecati nemo, fugiat libero tempore, sequi quisquam tempora
                optio velit neque blanditiis quis dolores perferendis provident
                aliquid, assumenda soluta. Porro consectetur eveniet neque esse
                maxime in quibusdam doloribus quos sit!
              </div>
              <div>
                Aliquam tempora, illum soluta molestiae sapiente praesentium,
                mollitia perspiciatis, dolorem cum dicta impedit doloribus
                aliquid consequuntur eos doloremque quod! Impedit obcaecati
                aliquam voluptas quam, doloribus placeat quas ipsam debitis ab!
              </div>
              <div>
                Recusandae deleniti cum harum placeat veniam doloremque,
                obcaecati amet aut sequi asperiores, quo omnis. Repellendus
                autem, ullam vero, voluptate inventore neque nobis similique
                tenetur quidem repellat veniam veritatis minus quo?
              </div>
              <div>
                Id optio ab recusandae distinctio! Quo corrupti incidunt alias
                fugiat quaerat sapiente numquam distinctio? Unde voluptas ab
                facilis cumque, tempore blanditiis quae. Odio voluptas eaque
                deserunt corporis, consequatur possimus minus!
              </div>
              <div>
                Animi officiis sunt accusamus voluptatem, aliquid enim corrupti
                ab voluptatibus, tempora numquam aspernatur nesciunt, cum velit?
                Deserunt mollitia, voluptas repellat vero libero, placeat
                voluptate reiciendis delectus totam, praesentium nostrum
                voluptatibus.
              </div>
              <div>
                Sed, voluptatum ad alias enim quam provident hic necessitatibus
                suscipit pariatur? Numquam vitae recusandae architecto fugit
                deserunt molestias, commodi alias eligendi ab veritatis nobis
                incidunt labore, reprehenderit possimus magni repellendus.
              </div>
              <div>
                Quidem quibusdam quae fugiat quod cupiditate ullam reiciendis
                iusto saepe animi eos, unde rem, tempore rerum aspernatur
                voluptatem error ratione dignissimos dolorum molestias aliquam
                voluptatibus tempora, repellendus provident odio? Quod!
              </div>
              <div>
                Similique excepturi modi illo enim perferendis exercitationem
                minus cum voluptates quod architecto maiores, reiciendis
                quisquam. Beatae sunt unde mollitia consequuntur molestiae saepe
                quis, exercitationem odio quidem natus veniam dolore vero.
              </div>
              <div>
                Quos fugit iure fugiat quaerat asperiores explicabo nam aperiam
                cupiditate vero nobis est recusandae ab molestias nemo, nostrum,
                numquam reprehenderit excepturi vitae itaque, rerum totam
                ratione. Consequatur tempora praesentium laudantium.
              </div>
              <div>
                Laborum voluptatibus enim consequuntur molestias ipsum. Fugit
                quibusdam quae beatae dolore dignissimos saepe rerum aut alias
                libero, ex doloribus rem dicta. Harum rem tempore doloribus.
                Illo error aliquam nam incidunt!
              </div>
              <div>
                Eaque ab corporis inventore impedit optio neque debitis
                consequatur a fugiat sint provident est nesciunt assumenda
                repellendus culpa praesentium, aspernatur ipsa! Repellendus
                tempora architecto beatae ducimus! Deleniti, reprehenderit?
                Praesentium, officia!
              </div>
              <div>
                Impedit iste tempore modi porro nobis exercitationem voluptatum
                eum quod voluptatibus harum accusantium ad ratione quia repellat
                distinctio id quas, nam numquam nemo molestias. Quae autem
                nostrum iste minus alias.
              </div>
              <div>
                Voluptates suscipit dignissimos non eos voluptate cum omnis!
                Voluptatibus eum quos quia nesciunt expedita vitae culpa laborum
                veritatis consectetur sequi, ipsa consequatur accusamus, dolorum
                repudiandae praesentium tempore quisquam, nulla harum.
              </div>
              <div>
                Sapiente, nobis fugiat ut perferendis sequi ullam fuga pariatur
                consectetur similique mollitia quidem unde incidunt autem dolore
                illum reiciendis! Voluptatum debitis quas a, beatae itaque velit
                porro sunt odio accusantium.
              </div>
              <div>
                Perferendis, magnam modi quam deserunt incidunt earum soluta
                aut, autem amet tempore voluptatibus libero. Sapiente, ipsam.
                Consequuntur ipsa doloribus placeat dolorem ipsam quia obcaecati
                excepturi. Ea quasi quas iusto ipsam?
              </div>
              <div>
                Aperiam velit nesciunt, molestias voluptatibus sint, saepe rerum
                numquam, corrupti amet voluptate quibusdam minus reiciendis in
                assumenda quod dicta. Voluptas neque esse accusamus explicabo
                voluptatem. Nisi fuga velit rerum a.
              </div>
              <div>
                Quisquam doloremque vitae amet velit explicabo aspernatur! Animi
                accusamus laboriosam deserunt ducimus aspernatur error ut atque.
                Accusantium voluptatibus praesentium, eveniet culpa minima
                adipisci architecto ab quibusdam modi qui tenetur voluptatem.
              </div>
              <div>
                Optio quia odit, aliquam nostrum id doloribus necessitatibus
                repellendus omnis veritatis laudantium repellat, ipsa sit
                suscipit sed ad harum dolores. Recusandae, quos nulla quia
                inventore aspernatur praesentium officia dicta quod!
              </div>
              <div>
                Voluptate numquam eveniet esse ratione ipsa nesciunt. Corrupti
                enim eaque commodi consectetur quis, adipisci temporibus, earum
                ad sapiente fugiat recusandae amet vitae necessitatibus
                architecto dolor quidem? Voluptas possimus modi ab.
              </div>
              <div>
                Perspiciatis rerum, ad amet ipsum aspernatur et sunt harum aut
                odit nihil nulla voluptas quibusdam consectetur cupiditate
                reprehenderit quae rem! Quisquam molestiae illo mollitia ea
                minus exercitationem atque possimus consequatur?
              </div>
              <div>
                Optio deserunt modi minima sint quisquam enim totam quis
                similique nisi eaque dolorum voluptatum quod a sunt possimus
                error eligendi, hic suscipit consectetur fugiat praesentium
                fuga. Animi ullam vero soluta?
              </div>
              <div>
                Neque sed praesentium voluptatibus magni, ex hic sint dolores
                quibusdam corrupti, ducimus placeat tenetur expedita sapiente
                aliquam numquam, nostrum voluptates? Corporis aut molestias
                deleniti, at aliquid aliquam iste dolores assumenda?
              </div>
              <div>
                Optio maxime eaque architecto laborum quisquam corporis quam hic
                explicabo! Mollitia consequatur vel blanditiis repellat tenetur
                molestias quisquam cum, ea aut impedit quibusdam fuga ipsum
                minus et? Aperiam, doloremque deserunt.
              </div>
              <div>
                Architecto dolorum tenetur numquam ullam temporibus quia fuga in
                quibusdam veniam sit illum laborum minus dolorem atque delectus,
                autem, ducimus, unde natus eveniet enim. Consequatur dignissimos
                exercitationem impedit perferendis et.
              </div>
              <div>
                Vero eos sit nam rem doloribus ut, nostrum distinctio natus
                molestias, provident consequatur esse exercitationem voluptas?
                Ex iure voluptatum inventore, commodi porro fugit quae obcaecati
                nam. Veniam tenetur cumque adipisci.
              </div>
              <div>
                Odit rem hic deserunt omnis inventore consequuntur soluta? Omnis
                dolore soluta unde, ratione accusantium officiis corrupti
                necessitatibus, facilis labore odit aliquam repudiandae
                explicabo neque aliquid commodi consectetur natus esse ad.
              </div>
              <div>
                Eos modi inventore a maxime, quasi numquam? Eligendi
                consequatur, officiis mollitia praesentium modi laboriosam illo
                itaque velit voluptatem accusantium ullam omnis, pariatur nam,
                enim quidem. Eos facilis tempore quae vitae.
              </div>
              <div>
                Ea ab ratione unde enim cum, culpa vel, perferendis eius facilis
                voluptatibus minima laboriosam natus. Provident asperiores
                repellat expedita voluptates quam rem, aspernatur ea, ratione
                natus dolorum, obcaecati impedit facere?
              </div>
              <div>
                Necessitatibus, laudantium. Possimus provident vitae at!
                Voluptatum esse recusandae sint iure. Animi quam, inventore
                cupiditate rerum totam impedit ea esse est veniam. Impedit harum
                ipsa rerum deserunt quibusdam omnis quam!
              </div>
              <div>
                Iste adipisci voluptatibus culpa, porro nam esse obcaecati ea
                debitis. Illo odio inventore fugiat a cupiditate nulla earum at
                blanditiis temporibus facere doloribus, cum dolor dolorem amet
                eius? Ducimus, eum!
              </div>
              <div>
                Ab amet obcaecati quas ratione aperiam ipsum eum eligendi eos?
                Esse repellat architecto perspiciatis distinctio quibusdam iste
                voluptates aut amet quaerat, beatae aliquam ipsa saepe vero quod
                nostrum veritatis quia?
              </div>
              <div>
                Consequatur cupiditate soluta repellat quidem. Doloribus vitae,
                cupiditate labore nesciunt rem quae quaerat, culpa harum quod
                quis blanditiis quia minus corrupti neque cum nemo voluptates
                quo voluptatem autem. Assumenda, cum!
              </div>
              <div>
                Ipsum accusamus qui, hic exercitationem alias consectetur ipsa
                voluptas sequi, culpa aliquid error fuga sunt! Qui adipisci quae
                pariatur! Repudiandae, officia? Nulla maiores et nobis facere
                perspiciatis veritatis, ratione odio?
              </div>
              <div>
                Nostrum provident voluptates consectetur perferendis molestias
                rem omnis pariatur dolores quam qui veniam, mollitia harum eum
                magnam laboriosam esse voluptas error perspiciatis libero optio
                quasi inventore, officiis aut at? Voluptatum.
              </div>
              <div>
                Eius, dolorum ut saepe reiciendis, ex ea consequuntur odio sint
                alias rem cumque nihil! Adipisci libero odit qui voluptate dolor
                commodi saepe nostrum nobis, expedita doloribus ut earum
                temporibus sunt!
              </div>
              <div>
                Laboriosam expedita quasi itaque quaerat alias reprehenderit,
                quam veniam ipsam aspernatur voluptate qui, explicabo rerum
                exercitationem sapiente, ipsa nesciunt voluptatem quibusdam
                possimus? Autem excepturi cum doloribus ex odio, eligendi
                quidem?
              </div>
            </div>
          </template>
        </Modal>

        <!-- modal BOTTOM -->
        <Modal position="bottom">
          <template #button>modal s tlacitkem - BOTTOM</template>
          <template #content>modal s tlacitkem</template>
        </Modal>

        <!-- modal s big image -->
        <Modal position="center">
          <template #button>BGIMG_button</template>
          <template #content>
            <img src="/big_image.webp" alt="velmi siroky obr" />
          </template>
        </Modal>

        <!-- modal s big image V -->
        <Modal position="fullscreen">
          <template #button>BGIMG_V__button</template>
          <template #content>
            <img src="/big_image_v.webp" alt="velmi vysoky obr" />
          </template>
        </Modal>

        <Dropdown>
          <template #button>button</template>
          <template #content>
            <div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">
                  123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                  12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                  joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123
                </li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div></template
          >
        </Dropdown>
      </div>
      <div class="rd w-screen absolute top-0 left-0">
        <Dropdown>
          <template #button>button</template>
          <template #content>
            <div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">
                  123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                  12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                  joij123 123 12o3i joij
                </li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute top-0 right-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute bottom-0 left-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute bottom-0 right-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
    </div>
    <div class="yl flex justify-center items-center w-svw h-dvh">
      <div class="flex flex-col gap-4">
        <button @click="isModalOpen = true">modal bez tlacitka - TOP</button>

        <!-- modal bez tlacitka -->
        <Modal v-model="isModalOpen" position="top" :showButton="false">
          <template #content>modal bez tlacitka</template>
        </Modal>

        <!-- modal fullscreen -->
        <Modal position="fullscreen">
          <template #button>modal s tlacitkem - fullscreen</template>
          <template #content>modal s tlacitkem</template>
        </Modal>

        <!-- modal BOTTOM -->
        <Modal position="bottom">
          <template #button>modal s tlacitkem - BOTTOM</template>
          <template #content>modal s tlacitkem</template>
        </Modal>

        <!-- modal s big image -->
        <Modal position="center">
          <template #button>BGIMG_button</template>
          <template #content>
            <img src="/big_image.webp" alt="velmi siroky obr" />
          </template>
        </Modal>

        <!-- modal s big image V -->
        <Modal position="center">
          <template #button>BGIMG_V__button</template>
          <template #content>
            <div class="overflow-auto">
              <img src="/big_image_v.webp" class="rd" alt="velmi vysoky obr" />
            </div>
          </template>
        </Modal>

        <Dropdown>
          <template #button>button</template>
          <template #content>
            <div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">
                  123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                  12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                  joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123
                </li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div></template
          >
        </Dropdown>
      </div>
      <div class="rd w-screen absolute top-0 left-0">
        <Dropdown>
          <template #button>button</template>
          <template #content>
            <div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">
                  123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                  12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                  joij123 123 12o3i joij
                </li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute top-0 right-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute bottom-0 left-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
      <div class="absolute bottom-0 right-0">
        <Dropdown>
          <template #button>button</template>
          <template #content
            ><div class="flex">
              <ul class="border">
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
                <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              </ul>
            </div>
          </template>
        </Dropdown>
      </div>
    </div>
  </div>
</template>

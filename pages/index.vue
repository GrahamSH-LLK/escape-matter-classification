<template>
  <div class="bg-gray-900 h-screen w-full text-white flex flex-col">
    <div class="flex-1"></div>
    <div>
      <div class="flex flex-row">
        <div
          class="
            bg-gray-700
            h-80
            w-48
            mx-5
            p-2
            relative
            border border-solid border-1
            flex flex-col
          "
        >
          <span
            class="
              absolute
              inset-y-0
              right-0
              my-24
              bg-gray-800
              border-white border-solid border-4
              rounded-full
              h-4
              w-4
              mx-2
            "
            :class="{
              'cursor-pointer': unlocked,
              'border-gray-300': !unlocked,
            }"
            @click="$vfm.show('unlockModal')"
          ></span>
        </div>
        <div class="w-full h-48 self-end flex flex-row">
          <div class="self-end flex-1 flex flex-col">
            <div class="flex w-full flex-1 self-end">
              <span class="self-end" @click="mixtureModalOpen = true"
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-20 w-20"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"
                  />
                </svg>
              </span>
              <span class="self-end" @click="$vfm.show('balancingModal')">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-20 w-20"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                  />
                </svg>
              </span>
              <span @click="$vfm.show('diagramModal')"
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  version="1.0"
                  width="1280.000000pt"
                  height="592.000000pt"
                  viewBox="0 0 1280.000000 592.000000"
                  preserveAspectRatio="xMidYMid meet"
                  class="h-20 w-48"
                >
                  <g
                    transform="translate(0.000000,592.000000) scale(0.100000,-0.100000)"
                    fill="#ffffff"
                    stroke="none"
                  >
                    <path
                      d="M9870 5600 c-79 -12 -125 -29 -186 -68 -79 -52 -129 -109 -173 -201 -35 -73 -36 -80 -36 -186 0 -106 1 -113 37 -187 39 -81 98 -154 155 -189 l34 -21 -2 -167 c-1 -91 -4 -220 -7 -287 l-4 -120 -44 -23 c-63 -34 -150 -130 -185 -206 -17 -36 -36 -98 -43 -138 l-12 -72 -160 -92 c-87 -51 -250 -145 -361 -209 l-202 -116 -67 27 c-122 49 -260 45 -384 -11 l-56 -25 -270 164 -269 164 -3 59 c-5 131 -74 272 -168 349 l-46 38 7 111 c3 61 11 176 16 255 l10 144 39 44 c166 189 111 469 -113 573 -83 39 -155 47 -237 26 -252 -65 -359 -344 -214 -557 l37 -54 -12 -230 c-7 -126 -14 -241 -17 -256 -3 -16 -25 -40 -66 -70 -102 -74 -179 -196 -195 -309 l-8 -55 -378 -190 -378 -191 -57 28 c-119 57 -262 63 -385 14 l-66 -27 -258 173 -258 173 -2 69 c-4 135 -57 253 -154 346 l-50 48 22 253 22 254 43 45 c24 25 56 72 71 105 24 52 28 72 28 150 0 78 -4 98 -27 145 -57 116 -153 189 -273 208 -262 42 -483 -205 -407 -455 12 -38 35 -88 52 -111 l30 -42 -22 -256 -22 -255 -68 -45 c-108 -72 -188 -197 -205 -321 l-6 -44 -378 -189 -378 -189 -43 24 c-106 59 -272 71 -386 27 l-54 -21 -301 201 c-166 110 -305 203 -309 207 -4 4 -12 40 -18 81 -43 313 -376 494 -656 356 -137 -68 -233 -202 -254 -354 -5 -39 -9 -78 -7 -84 1 -7 -83 -76 -187 -154 l-189 -142 -92 -4 c-114 -5 -183 -36 -255 -115 -64 -70 -92 -144 -92 -243 0 -107 29 -179 101 -250 77 -77 134 -102 241 -108 98 -5 165 15 239 70 56 41 116 134 132 204 l12 55 190 141 191 140 55 -13 c76 -19 184 -16 252 5 l56 18 312 -208 311 -207 0 -52 c0 -118 62 -248 161 -339 l68 -61 -25 -280 c-14 -154 -29 -282 -35 -283 -5 -2 -37 -22 -70 -45 -71 -46 -137 -130 -171 -215 -30 -76 -32 -230 -5 -310 43 -123 151 -235 275 -283 46 -19 76 -23 162 -23 124 0 187 20 275 87 243 185 245 548 3 734 l-27 20 24 274 c14 151 25 279 25 284 0 6 23 21 51 34 111 53 214 190 245 328 l15 69 375 187 374 187 50 -25 c125 -64 267 -71 394 -20 l68 27 259 -173 259 -174 0 -65 c0 -134 41 -231 143 -337 l59 -62 -22 -253 -22 -253 -40 -38 c-22 -21 -54 -69 -71 -105 -28 -59 -32 -78 -32 -152 0 -76 3 -93 32 -151 39 -79 102 -140 181 -177 49 -23 70 -27 147 -27 82 0 97 3 156 32 79 39 140 102 177 181 22 47 26 72 27 142 0 93 -15 142 -65 215 l-29 42 20 224 c27 307 18 278 94 328 66 43 125 111 163 187 19 37 28 69 46 156 5 23 48 48 381 217 l375 190 62 -29 c132 -62 277 -63 410 -3 l57 25 178 -107 c98 -60 220 -133 271 -164 l92 -56 0 -50 c0 -142 93 -316 205 -385 l35 -22 0 -392 0 -392 -47 -35 c-95 -71 -168 -201 -180 -323 l-6 -61 -190 -120 -191 -120 -100 0 c-88 0 -108 -3 -158 -27 -209 -98 -279 -346 -152 -535 42 -61 83 -95 161 -130 46 -21 71 -26 137 -26 87 0 143 18 219 70 51 36 113 123 128 182 l12 48 199 125 199 126 47 -21 c39 -18 65 -22 162 -22 105 0 120 2 177 29 34 15 66 27 70 25 5 -2 92 -48 194 -103 l186 -99 27 -63 c32 -73 110 -153 183 -187 69 -32 227 -32 296 0 70 33 150 113 183 186 25 53 29 75 29 147 0 75 -4 93 -31 150 -61 127 -167 200 -303 208 -42 2 -92 0 -112 -6 -35 -9 -46 -5 -232 94 l-195 104 -7 47 c-17 115 -92 241 -180 304 l-47 34 7 390 c7 385 7 390 28 404 12 8 47 40 78 71 69 69 115 162 131 263 l12 75 365 210 366 210 37 -19 c108 -55 244 -60 379 -13 l75 26 320 -185 319 -185 7 -48 c16 -111 60 -195 142 -272 154 -146 387 -167 568 -51 128 82 216 254 206 401 l-3 51 178 151 179 151 74 6 c83 7 118 19 187 62 135 84 195 274 137 430 -30 79 -104 158 -188 199 -58 29 -76 33 -147 32 -101 0 -174 -27 -244 -90 -57 -51 -108 -145 -119 -217 -7 -45 -11 -49 -191 -201 -102 -85 -188 -153 -193 -150 -5 3 -36 9 -68 14 -72 10 -176 -3 -236 -30 l-44 -19 -322 187 -322 187 -12 72 c-22 135 -100 258 -210 334 l-42 28 4 173 c3 95 7 223 10 284 l6 110 34 19 c43 23 122 107 157 165 75 128 75 322 0 450 -96 163 -285 258 -463 230z m70 -1009 c0 -47 -3 -150 -7 -228 -6 -130 -8 -143 -25 -143 -17 0 -18 12 -18 204 0 236 4 266 31 259 17 -5 19 -15 19 -92z m-4903 -1242 c109 -72 202 -135 208 -140 6 -6 3 -15 -7 -25 -14 -14 -34 -3 -231 128 -188 125 -214 146 -205 162 5 9 16 15 23 12 8 -3 103 -64 212 -137z m2763 -40 c118 -72 218 -134 223 -138 4 -4 1 -15 -6 -25 -12 -16 -30 -7 -239 120 -198 120 -225 140 -217 156 5 10 13 18 17 18 4 0 104 -59 222 -131z m-4930 -811 c0 -25 -31 -383 -36 -415 -4 -24 -10 -33 -24 -33 -24 0 -24 -15 -5 212 20 241 21 248 45 248 11 0 20 -6 20 -12z"
                    />
                  </g></svg
              ></span>
              <span @click="$vfm.show('mixtureNotebookModal')">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  aria-hidden="true"
                  role="img"
                  width="1em"
                  height="1em"
                  preserveAspectRatio="xMidYMid meet"
                  viewBox="0 0 32 32"
                  class="h-20 w-20"
                >
                  <path d="M19 10h7v2h-7z" fill="currentColor" />
                  <path d="M19 15h7v2h-7z" fill="currentColor" />
                  <path d="M19 20h7v2h-7z" fill="currentColor" />
                  <path
                    d="M28 5H4a2.002 2.002 0 0 0-2 2v18a2.002 2.002 0 0 0 2 2h24a2.003 2.003 0 0 0 2-2V7a2.002 2.002 0 0 0-2-2zM4 7h11v18H4zm13 18V7h11l.002 18z"
                    fill="currentColor"
                  />
                </svg>
              </span>
              <span @click="$vfm.show('pureSubstanceModal')">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  aria-hidden="true"
                  role="img"
                  width="1em"
                  height="1em"
                  preserveAspectRatio="xMidYMid meet"
                  viewBox="0 0 32 32"
                  class="h-20 w-20"
                >
                  <path d="M19 10h7v2h-7z" fill="currentColor" />
                  <path d="M19 15h7v2h-7z" fill="currentColor" />
                  <path d="M19 20h7v2h-7z" fill="currentColor" />
                  <path
                    d="M28 5H4a2.002 2.002 0 0 0-2 2v18a2.002 2.002 0 0 0 2 2h24a2.003 2.003 0 0 0 2-2V7a2.002 2.002 0 0 0-2-2zM4 7h11v18H4zm13 18V7h11l.002 18z"
                    fill="currentColor"
                  />
                </svg>
              </span>
              <span @click="$vfm.show('atomicModal')"
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  version="1.0"
                  width="1280.000000pt"
                  height="1131.000000pt"
                  viewBox="0 0 1280.000000 1131.000000"
                  preserveAspectRatio="xMidYMid meet"
                  class="h-20 w-20"
                >
                  <g
                    transform="translate(0.000000,1131.000000) scale(0.100000,-0.100000)"
                    fill="#fff"
                    stroke="none"
                  >
                    <path
                      d="M3505 11300 c-284 -42 -518 -215 -653 -485 -75 -150 -120 -307 -154 -530 -17 -119 -18 -618 0 -780 58 -533 193 -1120 402 -1758 38 -118 70 -219 70 -224 0 -6 -17 -14 -37 -17 -129 -23 -409 -85 -598 -132 -599 -149 -1051 -307 -1460 -509 -320 -158 -544 -307 -720 -480 -560 -549 -450 -1193 289 -1694 529 -358 1372 -664 2386 -866 74 -15 136 -28 138 -30 2 -2 -33 -112 -77 -246 -227 -690 -359 -1287 -402 -1823 -17 -219 -7 -607 20 -761 93 -526 308 -817 686 -931 80 -24 107 -27 245 -28 129 -1 173 3 260 22 465 105 964 401 1560 927 188 166 584 563 779 783 84 94 157 172 161 172 4 0 77 -78 161 -173 191 -214 589 -615 769 -773 559 -493 1040 -793 1457 -908 150 -41 223 -51 368 -51 171 0 249 17 390 85 300 145 471 425 552 905 15 91 18 165 18 430 0 332 -5 398 -51 705 -65 423 -192 931 -364 1449 -39 117 -69 215 -68 216 2 2 64 15 138 29 990 195 1859 510 2386 867 739 501 849 1146 289 1694 -454 444 -1390 835 -2600 1085 -115 24 -211 44 -213 45 -1 1 30 98 69 216 209 636 335 1178 401 1724 20 171 17 732 -5 860 -58 332 -152 558 -305 725 -63 69 -191 163 -267 195 -525 225 -1252 -65 -2170 -865 -175 -153 -616 -595 -799 -802 -82 -93 -152 -168 -156 -168 -3 0 -74 75 -155 168 -184 207 -626 649 -800 802 -540 473 -1040 780 -1450 890 -165 44 -356 60 -490 40z m295 -335 c572 -93 1409 -723 2274 -1712 l107 -122 -135 -169 c-254 -320 -585 -774 -800 -1097 l-66 -101 -178 -13 c-399 -28 -938 -89 -1325 -150 -159 -24 -179 -26 -186 -12 -5 9 -43 120 -84 246 -491 1499 -538 2634 -126 3010 130 118 294 156 519 120z m5482 1 c105 -23 175 -61 254 -140 84 -85 131 -165 178 -306 180 -543 62 -1501 -329 -2690 l-85 -256 -112 18 c-160 26 -512 73 -723 97 -212 25 -738 71 -799 71 l-42 0 -116 173 c-220 327 -505 716 -755 1030 l-134 168 112 127 c395 450 827 868 1169 1133 569 441 1056 644 1382 575z m-2785 -2218 c180 -226 585 -773 686 -928 l16 -25 -799 0 c-529 0 -796 3 -792 10 13 21 199 285 276 390 197 272 503 665 516 665 4 0 48 -51 97 -112z m853 -1296 l85 -7 118 -185 c165 -258 407 -665 552 -925 149 -268 358 -666 358 -680 0 -14 -211 -415 -358 -680 -146 -262 -388 -667 -552 -925 l-118 -185 -125 -9 c-163 -12 -1658 -12 -1820 0 l-124 9 -93 145 c-285 444 -608 1002 -856 1480 l-86 164 71 136 c307 584 609 1108 893 1544 l75 116 52 1 c29 1 132 5 228 9 200 9 1572 2 1700 -8z m-2402 -40 c-1 -4 -61 -101 -131 -215 -206 -336 -416 -704 -613 -1074 -27 -51 -52 -93 -55 -93 -21 0 -552 1220 -537 1235 13 13 689 98 1068 134 225 22 273 24 268 13z m3152 -12 c433 -40 1062 -118 1079 -135 14 -15 -286 -727 -463 -1100 l-67 -140 -56 105 c-190 358 -451 813 -644 1124 -55 87 -99 160 -99 162 0 6 24 5 250 -16z m-4740 -377 c147 -379 308 -749 505 -1164 l97 -202 -93 -191 c-183 -379 -364 -792 -504 -1151 -43 -110 -81 -203 -84 -207 -3 -4 -91 11 -196 32 -999 201 -1818 502 -2296 846 -104 75 -254 217 -315 297 -226 301 -184 584 133 887 369 354 1085 670 2048 906 167 41 591 132 621 133 6 1 43 -83 84 -186z m6440 130 c1109 -230 1980 -587 2393 -983 313 -300 357 -571 142 -875 -55 -78 -219 -234 -324 -309 -484 -346 -1299 -646 -2296 -847 -104 -21 -193 -35 -196 -31 -3 4 -41 97 -84 207 -141 361 -320 769 -504 1151 l-93 191 55 109 c183 365 462 1008 616 1416 12 32 -18 35 291 -29z m-5626 -1910 c79 -166 436 -793 645 -1132 72 -118 131 -216 131 -218 0 -21 -1305 129 -1328 152 -6 6 44 139 150 393 122 295 368 841 379 842 3 0 13 -17 23 -37z m4543 -100 c179 -378 476 -1083 461 -1098 -14 -14 -556 -84 -918 -119 -345 -33 -410 -39 -410 -33 0 3 44 76 98 164 201 322 473 796 638 1110 32 62 60 113 62 113 2 0 33 -62 69 -137z m667 -1663 c391 -1185 508 -2142 330 -2689 -46 -141 -93 -222 -178 -307 -137 -136 -295 -178 -536 -139 -571 93 -1392 710 -2269 1707 l-112 127 135 169 c249 313 593 785 800 1098 l67 101 107 7 c277 18 704 61 1047 106 131 17 515 75 522 79 1 1 40 -116 87 -259z m-5678 225 c357 -56 929 -121 1296 -146 l177 -13 67 -100 c205 -310 562 -799 813 -1114 l122 -153 -112 -127 c-883 -1002 -1697 -1614 -2273 -1707 -240 -39 -396 3 -536 144 -85 86 -139 183 -184 331 -145 482 -67 1294 220 2280 42 143 191 605 201 623 7 11 39 9 209 -18z m3486 -200 c-9 -17 -140 -202 -235 -335 -190 -264 -543 -720 -557 -720 -22 0 -649 833 -783 1040 l-16 25 799 0 c529 0 796 -3 792 -10z"
                    />
                    <path
                      d="M6275 6346 c-253 -50 -462 -231 -542 -470 -24 -71 -27 -97 -27 -216 -1 -123 2 -143 28 -224 73 -223 266 -403 496 -463 87 -23 253 -23 340 0 167 44 326 158 422 306 132 202 144 475 31 701 -56 112 -189 243 -303 299 -47 22 -112 48 -145 56 -87 22 -218 27 -300 11z"
                    />
                  </g></svg
              ></span>
              <span @click="$vfm.show('solutionModal')">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-20 w-20"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                  />
                </svg>
              </span>
              <span @click="$vfm.show('periodModal')">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-20 w-20"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                  />
                </svg>
              </span>
            </div>
            <div
              class="
                h-32
                w-full
                bg-gray-500
                h-32
                self-end
                border-gray-600 border-t-8
              "
            ></div>
          </div>
        </div>
      </div>
      <div class="h-32 flex-1 bg-gray-600"></div>
    </div>
    <Modal v-model="showWelcomeModal" name="welcomeModal">
      <template v-slot:title>Welcome to the lab 🧪</template>
      <p>
        I sure hope you know your classification of matter, because without it,
        you'll be stuck in here forever. You have as much time as you need to
        use your science knowledge open the 5 locks and get out.
      </p>
    </Modal>
    <Modal v-model="unlockModalOpen" name="unlockModal">
      <template v-slot:title>{{ unlockModalTitle }}</template>
      <p>{{ unlockModalBody }} {{ challengesDone }}/8</p>
    </Modal>
    <Modal v-model="mixtureModalOpen" name="mixtureModal">
      <template v-slot:title>You look in the beaker and see...</template>
      <p>
        a cloudy liquid. The beaker has dust, so it looks like it's been sitting
        in there for a while. On the table behind of it, you see a note that
        says:
      </p>
      <div
        class="
          bg-yellow-300
          p-3
          border border-yellow-400 border-2
          w-60
          text-black
          italic
        "
      >
        The first puzzle is here. You have all the information you need to
        complete this.
        <p>To unlock this, fill in the blank</p>
        <p>The liquid is a ____</p>
      </div>
      <BeakerRiddle
        @correct="beakerHandler(true)"
        @wrong="beakerHandler(false)"
      ></BeakerRiddle>
    </Modal>
    <Modal v-model="balancingModalOpen" name="balancingModal">
      <template v-slot:title>You see a piece of paper</template>
      <p>
        on the counter. It has a chemical equation that has been balanced. You
        take one look at it and notice it’s wrong.
      </p>
      <p>The balancing looks like this:</p>
      <p>2O + La ---> OLa</p>
      <p>2O + La ---> O<sub>2</sub>La</p>

      <p>
        1. You can’t do this because changing the ___ of the chemical symbol
        changes the whole element.
      </p>
      <p class="whitespace-pre">
        Red: Coefficient Blue: Subscript Green: Formula Yellow: Symbol
      </p>
      <p>2. What would the correct balancing look like?</p>
      <p class="whitespace-pre">
        Red: 2O + 2La ---> 2OLa Blue: 2O + La ---> O<sub>2</sub>La Green: 4O +
        4La ---> 4OLa Yellow: 4O + 4La ---> 3OLa
      </p>

      <BalancingRiddle @response="balancingHandler"></BalancingRiddle>
    </Modal>
    <Modal v-model="diagramModalOpen" name="diagramModal">
      <template v-slot:title>You see a diagram of a compound</template>
      <img src="~/assets/diagram.png" />
      <p>1. What is the chemical formula for this compound?</p>
      <p class="whitespace-pre">
        Square: 2HO Triangle: H2O Circle: HO2 Hexagon: 2H2O
      </p>

      <p>2. How many Hydrogen atoms does this compound have?</p>
      <p class="whitespace-pre">Square: 2 Triangle: 3 Circle: 4 Hexagon: 0</p>
      <p>3. H<sub>2</sub>O is a pure substance</p>
      <p class="whitespace-pre">Square: False Circle: True</p>

      <DiagramRiddle @response="diagramHandler"></DiagramRiddle>
    </Modal>

    <Modal v-model="mixtureNotebookModalOpen" name="mixtureNotebookModal">
      <template v-slot:title>You see scribblings in a notebook</template>
      <p>
        about mixtures, but you can’t quite read them. However, you know a lot
        about mixtures and can fill in the blanks.
      </p>
      <p class="whitespace-pre">
        Homogenous Mixture: North Heterogenous Mixture: South Colloid: East
        Solution: West Alloy: North
      </p>

      <p class="italic">
        Mixtures are the key to my success, muahahaha. I eat _______ in the form
        of mixed nuts to satisfy my hunger. To build my doomsday devices, I use
        stainless steel for that shiny look. It’s an _______ (a metal _______).
        Whereas ______s are clear, ______s are cloudy. They are both ____s.
      </p>
      <p>3. H<sub>2</sub>O is a pure substance</p>
      <p class="whitespace-pre">Square: False Circle: True</p>

      <NotebookMixtureRiddle
        @response="notebookMixtureHandler"
      ></NotebookMixtureRiddle>
    </Modal>
    <Modal v-model="pureSubstanceModalOpen" name="pureSubstanceModal">
      <template v-slot:title>In another notebook</template>
      <p>
        you see more scribblings, this time about pure substances. This mad
        scientist’s handwriting is really bad!
      </p>
      <p class="whitespace-pre">
        1: pure substances 2: compounds 3: atoms 4: mixtures 5: elements 6:
        molecules
      </p>

      <p class="italic">
        I also use many _____ in my daily life. For example, I drink water, a
        _______. ______ are a form of _________, along with ____. Compounds make
        up _____. Elements, however are made up of _____. _____ are made of pure
        substances.
      </p>

      <PureSubstanceRiddle
        @response="pureSubstanceHandler"
      ></PureSubstanceRiddle>
    </Modal>
    <Modal name="atomicModal" v-model="atomicModalOpen">
      <template v-slot:title>You notice a slip of paper that says </template>
      Water is a triatomic molecule. CO2 is also a triatomic molecule. O2 is a
      diatomic particle. Br2 is a diatomic molecule.
      <AtomicRiddle @response="atomicHandler"></AtomicRiddle>
    </Modal>

    <Modal name="solutionModal" v-model="solutionModalOpen">
      <template v-slot:title>You notice an unfinished page </template>
      <p class="whitespace-pre">
        Solute: 1 Solvent: 0 Water is the universal ______ In sugar water, sugar
        is the ______ In a solution, there is a solvent and a _____ In
        saltwater, water is the _____
      </p>
      <SolutionRiddle @response="solutionHandler"></SolutionRiddle>
    </Modal>
    <Modal name="periodModal" v-model="periodModalOpen">
      <template v-slot:title>Last lock!</template>
      <img src="~/assets/period.png" />
      <p class="whitespace-pre">
        Red: Atomic Mass Blue: Atomic Number Green: Chemical Symbol
      </p>
      <PeriodRiddle @response="periodHandler"></PeriodRiddle>
    </Modal>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showWelcomeModal: true,
      challenges: {
        beakerRight: false,
        balancingRight: false,
        diagramRight: false,
        mixtureRight: false,
        pureSubstanceRight: false,
        atomicRight: false,
        solutionRight: false,
        periodRight: false,
      },
      unlockModalOpen: false,
      mixtureModalOpen: false,
      balancingModalOpen: false,
      diagramModalOpen: false,
      mixtureNotebookModalOpen: false,
      pureSubstanceModalOpen: false,
      atomicModalOpen: false,
      solutionModalOpen: false,
      periodModalOpen: false,
    };
  },
  watch: {
    unlocked() {
      if (this.unlocked) {
        this.$vfm.show('unlockModal');
      }
    },
  },
  computed: {
    unlockModalTitle() {
      if (this.unlocked) {
        return 'Well done! You escaped the lab!';
      }
      return "Sorry, you haven't solved everything";
    },
    unlockModalBody() {
      if (this.unlocked) {
        return 'I guess you know your matter classifications!';
      }
      return "Keep going, and maybe you'll make it out!";
    },
    unlocked() {
      return Object.values(this.challenges).every(Boolean);
    },
    challengesDone() {
      return Object.values(this.challenges).reduce((a, item) => a + item, 0)

    }
  },
  methods: {
    beakerHandler(correct) {
      this.challenges.beakerRight = correct;
      this.mixtureModalOpen = !correct;
    },
    balancingHandler(e) {
      this.challenges.balancingRight = e;
      this.balancingModalOpen = !e;
    },
    diagramHandler(e) {
      this.challenges.diagramRight = e;
      this.diagramModalOpen = !e;
    },
    notebookMixtureHandler(e) {
      this.challenges.mixtureRight = e;
      this.mixtureNotebookModalOpen = !e;
    },
    pureSubstanceHandler(e) {
      this.challenges.pureSubstanceRight = e;
      this.pureSubstanceModalOpen = !e;
    },
    atomicHandler(e) {
      this.challenges.atomicRight = e;
      this.atomicModalOpen = !e;
    },
    solutionHandler(e) {
      this.challenges.solutionRight = e;
      this.solutionModalOpen = !e;
    },
    periodHandler(e) {
      this.challenges.periodRight = e;
      this.periodModalOpen = !e;
    },
  },
};
</script>
<style>
input {
  @apply p-2 rounded;
}
</style>

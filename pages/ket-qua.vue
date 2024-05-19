

<script setup lang="ts">
    const tabs = ref([{
        lable: 'Kỹ sư khoa học dữ liệu',
        value: '1',
    }, {
        lable: 'Kỹ sư học máy',
        value: '2',
    }, {
        lable: 'Kỹ sư phân tích dữ liệu',
        value: '3',
    }, {
        lable: 'Kỹ sư dữ liệu lớn',
        value: '4',
    }, {
        lable: 'Quản trị cơ sở dữ liệu',
        value: '5',
    }, {
        lable: 'Lập trình viên BI',
        value: '6',
    }])

    const currentTab = ref('3')
</script>


  
  <template>
    <div>
      <!--HEADING -->
      <div class="flex flex-col items-center justify-center gap-8 mt-8">
        <div
          class="flex items-center gap-4 bg-[#FBFAF9] justify-center w-fit px-[20px] rounded-[20px] border-[1px] border-[#EBEAE9] py-2"
        >
          <p class="m-0 text-black">Kết quả đánh giá</p>
        </div>
        <h1 class="text-center font-semibold text-black text-[24px] sm:text-[40px]">
          Khoa học máy tính
        </h1>
        <p class="text-center text-[18px] font-[400]">
          Là lĩnh vực phù hợp với bạn, các vị trí nghề nghiệp cụ thể của ngành<br />
          mà bạn có thể làm được liệt kê dưới đây
        </p>
      </div>
      <!-- FEATURE -->
      
      <div class="container pt-14">
        <div class="grid grid-cols-1 md:grid-cols-5 gap-5">
        <div class="md:col-span-2 order-2 md:order-none">
          <ul class="sm:w-72 mt-5">
            <li 
                v-for="tab, index in tabs" :key="index"
                class="text-black font-medium text-base sm:text-xl p-3 md:p-5 cursor-pointer" 
                :class="[currentTab === tab.value && 'text-white bg-[#00237D]']"
                @click="currentTab = tab.value"
            >
                {{ tab.lable }}
            </li>
          </ul>
        </div>
        <div class="md:col-span-3 order-1 md:order-none">
          <div class="group relative rounded-2xl sm:col-span-2 bg-[#F4F2F0] border-[#EBEAE9] bg-cover min-h-[300px] md:min-h-[450px] w-full bg-[url('/assets/images/khoa-hoc-may-tinh.png')]"
          >
            <div class="opacity-0 transition-all duration-300 group-hover:opacity-100 bg-black/50 p-6 absolute w-full h-full  flex flex-col justify-end rounded-2xl">
                <h5 class="text-white text-xl md:text-3xl font-semibold mb-3">Khoa học dữ liệu</h5>
                <p class="m-0 text-white font-light md:text-2xl">
                    Khoa học máy tính là ngành nghiên cứu các cơ sở lý thuyết về thông
                    tin và tính toán cùng sự thực hiện và ứng dụng của chúng trong các
                    hệ thống máy tính.
                </p>

                <nuxt-link to="/chi-tiet-nghe-nghiep/khoa-hoc-may-tinh" class="mt-5">
                    <span class="font-semibold !bg-transparent !border-white !text-white border-[1px] border-solid gap-1 !flex items-center justify-center !p-0 !w-[267px] !h-12 !rounded-3xl">
                        Bắt đầu gợi ý nghề nghiệp
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="24"
                            height="25"
                            viewBox="0 0 24 25"
                            fill="none"
                        >
                        <path
                            d="M17.25 8.75L21 12.5M21 12.5L17.25 16.25M21 12.5H3"
                            stroke="#ffffff"
                            stroke-width="1.5"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        </svg>
                    </span>
                </nuxt-link>
            </div>
          </div>
        </div>
      </div>
      </div>
  
      <!-- CATEGORIES -->
      <div class="bg-white">
        <div class="container py-14 w-full relative">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-12 pb-12">
            <div>
              <div
                class="flex items-center gap-4 bg-[#FBFAF9] justify-center w-fit px-[20px] rounded-[20px] border-[1px] border-[#EBEAE9] py-2"
              >
                <p class="m-0 text-black">Giới thiệu</p>
              </div>
              <h4 class="font-[700] text-black text-[40px] mt-6 leading-[44px]">
                Ngành<br />
                Khoa học máy tính
              </h4>
            </div>
            <div>
              <h6 class="font-semibold text-2xl text-black ">
                Khoa học máy tính (tiếng Anh: Computer Science) là ngành nghiên cứu các cơ sở lý thuyết về thông tin và tính toán cùng sự thực hiện và ứng dụng của chúng trong các hệ thống máy tính. 
              </h6>
              <p class="text-[#8B898C] font-[400] mt-8">
                Khoa học máy tính là cách tiếp cận khoa học và thực tiễn để tính toán và các ứng dụng của nó và nghiên cứu có hệ thống về tính khả thi, cấu trúc, biểu hiện và cơ giới hóa các thủ tục (hoặc các thuật toán) cơ bản làm cơ sở cho việc thu thập, đại diện, xử lý, lưu trữ, truyền thông và truy cập thông tin. 
              </p>
              <p class="text-[#8B898C] font-[400] mt-8">
                Nói cách khác, khoa học máy tính là nghiên cứu về các quy trình thuật toán tự động hóa mà có thể nhân rộng trên quy mô lớn. Một nhà khoa học máy tính là chuyên gia về lý thuyết tính toán và thiết kế các hệ thống tính toán.
              </p>
            </div>
          </div>
        </div>
      </div>
      <!-- CATEGORIES -->
      <div class="bg-[#FBFAF9]">
        <div class="container py-14 w-full relative">
          <div
            class="flex items-center bg-white justify-center w-fit px-[20px] rounded-[20px] border-[1px] border-[#ebeae9] py-2"
          >
            <p class="m-0 text-black">Tương tự</p>
          </div>
          <h4 class="font-[700] text-black text-[40px] mt-6">Các ngành con</h4>
  
          <div class="grid grid-cols-2 md:grid-cols-3 gap-6 mt-12 pb-12">
            <div
              v-for="e in 9"
              :key="e"
              class="rounded-[12px] flex items-start justify-between p-4 bg-white"
            >
              <div>
                <h6 class="text-black text-[18px] font-[500] mb-[2px]">
                  Kỹ sư Học máy
                </h6>
                <p class="text-black text-[14px]">Machine Learning Engineer</p>
              </div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="18"
                height="18"
                viewBox="0 0 18 18"
                fill="none"
              >
                <path
                  d="M1.5 16.5L16.5 1.5M16.5 1.5L5.25 1.5M16.5 1.5V12.75"
                  stroke="black"
                  stroke-width="1.5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </div>
          </div>
        </div>
      </div>
      <!-- FOOTER -->
      <Footer />
    </div>
  </template>
  
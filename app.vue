<script setup>
const menus = [
  {
    title: 'ข่าวสาร',
    link: 'https://google.com',
    subMenu: [
      { title: 'ข่าวเกี่ยวกับหอการค้าไทย', link: 'https://google.com' },
      { title: 'คลังความรู้ธุรกิจ', link: 'https://google.com' },
      { title: 'ข่าวฝากประชาสัมพันธ์', link: 'https://google.com' },
      { title: 'ศูนย์พยากรณ์เศรษฐกิจ ฯ', link: 'https://google.com' },
      { title: 'อื่น ๆ ', link: 'https://google.com' },
    ],
  },
  {
    title: 'กิจกรรม',
    link: 'https://google.com',
    subMenu: [
      { title: 'งานแสดงสินค้าและจับคู่ธุรกิจ', link: 'https://google.com' },
      { title: 'กิจกรรมพัฒนาผู้ประกอบการ', link: 'https://google.com' },
      { title: 'กิจกรรมเพื่อสังคม', link: 'https://google.com' },
      { title: 'Exclusive สำหรับสมาชิก', link: 'https://google.com' },
      { title: 'ปฏิทินกิจกรรม', link: 'https://google.com' },
      { title: 'ประมวลกิจกรรมของคณะกรรมการ', link: 'https://google.com' },
      { title: 'อื่น ๆ ', link: 'https://google.com' },
    ],
  },
  {
    title: 'บริการ',
    link: 'https://google.com',
    subMenu: [
      { title: 'APEC Card', link: 'https://google.com' },
      { title: 'CO/Legalization ', link: 'https://google.com' },
      { title: 'ATA Carnet', link: 'https://google.com' },
      { title: 'CSC', link: 'https://google.com' },
      { title: 'รับรองฐานะทางการเงิน', link: 'https://google.com' },
      { title: 'อนุญาโตตุลาการ', link: 'https://google.com' },
    ],
  },
  {
    title: 'สิทธิประโยชน์',
    link: 'https://google.com',
    subMenu: [
      { title: 'TCC Connect', link: 'https://google.com' },
      { title: 'แหล่งเงินทุน', link: 'https://google.com' },
      {
        title: 'สิทธิประโยชน์ด้านการศึกษาจาก UTCC',
        link: 'https://google.com',
      },
      { title: 'SMEs Pro-active ของ ฝ่ายสมาชิก', link: 'https://google.com' },
      { title: 'อื่น ๆ ', link: 'https://google.com' },
    ],
  },
  {
    title: 'เกี่ยวกับเรา',
    link: 'https://google.com',
    subMenu: [
      { title: 'นโยบายหลัก', link: 'https://google.com' },
      { title: 'โครงสร้างองค์กร', link: 'https://google.com' },
      { title: 'เครือข่าย', link: 'https://google.com' },
      { title: 'ประวัติองค์กร', link: 'https://google.com' },
      { title: 'พ.ร.บ  ข้อบังคับ และจรรยาบรรณ', link: 'https://google.com' },
      { title: 'คุ้มครองส่วนบุคคล', link: 'https://google.com' },
      { title: 'สรุปผลงานคณะกรรมการ ประจำปี xxx', link: 'https://google.com' },
      { title: 'จัดซื้อจัดจ้าง และ เอกสารเผยแพร่', link: 'https://google.com' },
      { title: 'สมัครงาน', link: 'https://google.com' },
    ],
  },
  {
    title: 'ติดต่อเรา',
    link: 'https://google.com',
    subMenu: [
      { title: 'ที่อยู่', link: 'https://google.com' },
      { title: 'Google maps', link: 'https://google.com' },
      { title: 'Social media', link: 'https://google.com' },
      { title: 'อื่นๆ', link: 'https://google.com' },
    ],
  },
  {
    title: 'สมัครสมาชิก ',
    link: 'https://google.com',
    subMenu: [
      { title: 'หน้ารวมการสมัครสมาชิก', link: 'https://google.com' },
      { title: 'ประเภทสมาชิก', link: 'https://google.com' },
      { title: 'สิทธิประโยชน์', link: 'https://google.com' },
      {
        title: 'การยืนยันตัวตน Verify  TCC Connect',
        link: 'https://google.com',
      },
      { title: 'อื่น ๆ ', link: 'https://google.com' },
    ],
  },
];
</script>

<template>
  <main class="container mx-auto">
    <nav>
      <ul class="flex gap-10 justify-center p-3 bg-gray-300 relative">
        <li v-for="item in menus" :key="item" class="group">
          <NuxtLink :to="item.link" target="_blank">{{ item.title }}</NuxtLink>

          <!-- Mega Menu -->
          <div
            class="bg-red-200 w-full h-100 absolute left-0 top-12 p-3 opacity-0 invisible transition-all duration-300 group-hover:opacity-100 group-hover:visible"
          >
            <div v-for="subMenu in item.subMenu" :key="subMenu.title">
              <NuxtLink :to="subMenu.link" target="_blank">
                {{ subMenu.title }}</NuxtLink
              >
            </div>
          </div>
        </li>
      </ul>
    </nav>
  </main>
</template>

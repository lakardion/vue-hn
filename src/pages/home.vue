<script setup lang="ts">
// const [page, setPage] = useState(1);
import { getNews } from "../services";
// const getNewsByPage = useCallback(() => {
//   return getNews({ page });
// }, [page]);
// const { data: news } = useService(getNewsByPage);

// console.log(news);
const news = await getNews();
</script>

<template>
  <main className="p-1.5">
    <header className="bg-orange-600 flex gap-1 p-1 items-center">
      <div className="border-2 border-white px-1.5">
        <p className="text-white">Y</p>
      </div>
      <p className="bg-orange-100/50">Hacker News</p>
    </header>
    <section className="flex-grow">
      <ul className="flex flex-col gap-3">
        <li v-for="n in news">
          {{ n.title }}
        </li>
      </ul>
    </section>
  </main>
</template>

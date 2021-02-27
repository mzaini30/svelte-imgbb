# Svelte Imgbb

Menggunakan imgbb API untuk upload gambar.

## Instalasi

```bash
npm i svelte-imgbb
```

## Menggunakan

```html
<img src={gambarnya}>
<Imgbb {key} bind:output={gambarnya} />

<script type="text/javascript">
	import Imgbb from 'svelte-imgbb'
	let gambarnya = 'kucing.jpg'
	const key = 'kajviam38akjkd93'
</script>
```

## Catatan

Untuk `key`, bisa diambil dari https://api.imgbb.com/
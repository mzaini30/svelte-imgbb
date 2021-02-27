<input type="file" bind:files class="d-block" accept="image/*" name="">

<script type="text/javascript">
	export let key
	export let output
	let files = `file_${Math.random()}`
	import {toBase64} from 'kumpulan-tools'
	const server = 'https://api.imgbb.com/1/upload'
	$: if (files) {
        async function upload(){
            let gambarnya = await toBase64(files[0])
            const body = new FormData
            body.append('key', key)
            body.append('image', gambarnya)
            let hasilnya = await fetch(server, {
                method: 'post',
                body
            }).then(x => x.json())
            hasilnya = await hasilnya
            output = hasilnya.data.url
        }
        upload()
    }
</script>
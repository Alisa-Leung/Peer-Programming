<script>
    let {title, image = "mag.png", alt, description} = $props();
</script>

<h1>{title}</h1>
<img src={image} alt={alt}>
<p>{description}</p>
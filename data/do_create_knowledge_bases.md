Title: Live Content

Description: Fetched live

Source: https://docs.digitalocean.com/products/knowledge-bases/how-to/create/

---

<!doctype html>
<html lang="en">
<head>
    
<script>
if (window.self !== window.top) {
     
    document.documentElement.dataset.theme = 'light';
} else if (localStorage.pdocsTheme) {
    document.documentElement.dataset.theme = localStorage.pdocsTheme;
}
</script><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="color-scheme" content="light dark"><meta name="description" content="Create a knowledge base by choosing an embeddings model, adding data sources, configuring chunking, and selecting an OpenSearch database.">

<meta name="generator" content="Hugo 0.161.1">

<meta name="google-site-verification" content="CAYPZwe7daX8KlYYZfB4VMjfT4g8Tqrrc4Q3g_wMvI8">

<meta name="og:site_name" content="DigitalOcean">
<meta name="og:type" content="article">

<meta name="twitter:site" content="DigitalOcean">
<meta name="twitter:creator" content="@DigitalOcean">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:url" content="https://docs.digitalocean.com/products/knowledge-bases/how-to/create/">

<link rel="canonical" href="https://docs.digitalocean.com/products/knowledge-bases/how-to/create/">
<meta name="keywords" content="DigitalOcean, cloud computing">
<script type="application/ld+json">{
  "@context": "https://schema.org",
  "@type": "TechArticle",
  "about": {
    "@type": "Thing",
    "name": "knowledge-bases"
  },
  "author": {
    "@type": "Organization",
    "name": "DigitalOcean",
    "url": "https://www.digitalocean.com"
  },
  "dateModified": "2026-04-15",
  "datePublished": "2026-04-23",
  "description": "Create a knowledge base by choosing an embeddings model, adding data sources, configuring chunking, and selecting an OpenSearch database.",
  "headline": "How to Create DigitalOcean Knowledge Bases",
  "image": "https://www.digitalocean.com/_next/static/media/intro-to-cloud.d49bc5f7.jpeg",
  "inLanguage": "en",
  "keywords": "DigitalOcean, cloud computing",
  "mainEntityOfPage": {
    "@id": "https://docs.digitalocean.com/products/knowledge-bases/how-to/create/",
    "@type": "WebPage"
  },
  "publisher": {
    "@type": "Organization",
    "logo": {
      "@type": "ImageObject",
      "url": "https://www.digitalocean.com/_next/static/media/logo.b31e883e.svg"
    },
    "name": "DigitalOcean"
  }
}
</script>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.min.css"><link rel="stylesheet" href="/css/bundle.min.038539e0589af5e6d03d36e32d6f07bcb72f25507d72ce3549aa83a33e4fa557.css" integrity="sha256-A4U54Fia9ebQPTbjLW8HvLcvJVB9cs41SaqDoz5PpVc=">
<link rel="shortcut icon" type="image/png" href="/favicon.png">
<title>How to Create DigitalOcean Knowledge Bases | DigitalOcean Documentation</title>

</head>

<body>

    
    <script>
    if (window.top !== window.self) {
        document.body.classList.add('in-iframe');
        document.addEventListener('DOMContentLoaded', function() {
            document.querySelectorAll('a').forEach(function(a) {
                a.target = '_blank';
                a.rel = 'noopener';
            });
        });
    }
    </script>

    
    




    



    



    
    <header id="top-nav" class="pico container-fluid"><nav>
    
    <button id="mobile-menu" class="mobile-nav">
        <i class="fa-solid fa-bars"></i>
    </button>

    
    <ul>
        <li id="top-nav-title-logo" >
            <a href="https://docs.digitalocean.com/"><div id="logo"><?xml version="1.0" encoding="UTF-8"?>
<svg enable-background="new 65.2 173.5 180 180" version="1.1" viewBox="65.2 173.5 180 180" xml:space="preserve" xmlns="http://www.w3.org/2000/svg">
<style type="text/css">
	.st0{fill:#0080FF;}
</style>

	
		
			
				
					
						<path class="st0" d="m155.2 351.7v-34.2c36.2 0 64.3-35.9 50.4-74-5.1-14.1-16.4-25.4-30.5-30.5-38.1-13.8-74 14.2-74 50.4h-34.1c0-57.7 55.8-102.7 116.3-83.8 26.4 8.3 47.5 29.3 55.7 55.7 18.9 60.6-26 116.4-83.8 116.4z"/>
					
					<polygon class="st0" points="155.3 317.6 121.3 317.6 121.3 283.6 121.3 283.6 155.3 283.6 155.3 283.6"/>
					<polygon class="st0" points="121.3 343.8 95.1 343.8 95.1 343.8 95.1 317.6 121.3 317.6"/>
					<path class="st0" d="m95.1 317.6h-21.9v-21.9h21.9v21.9z"/>
				
			
		
	

</svg>
</div><span>DigitalOcean | Docs</span>
            </a>
        </li>
    </ul>

    <ul>
        <li>
            
            <input id="top-nav-search" type="search" name="search" placeholder="Search" aria-label="Search"/>
        </li>
    </ul>

    <ul><li class="top-nav-section-links not-mobile-nav">
            <a href="https://docs.digitalocean.com/platform/">Platform</a>
        </li><li class="top-nav-section-links not-mobile-nav active">
            <a href="https://docs.digitalocean.com/products/" class="active" aria-current="page">Products</a>
        </li><li class="top-nav-section-links not-mobile-nav">
            <a href="https://docs.digitalocean.com/reference/">Reference</a>
        </li><li class="top-nav-section-links not-mobile-nav">
            <a href="https://docs.digitalocean.com/support/">Support</a>
        </li>
        <li id="sign-up" class="not-mobile-nav">
            <a href="https://cloud.digitalocean.com/registrations/new"><button>Sign Up</button></a>
        </li>
        <li>
            <button id="light-dark-toggle" class="outline not-mobile-nav">
            </button>
        </li>
    </ul>
</nav>

    </header>
    

    <div class="main-grid">
        <aside id="left-nav" class="pico"><nav id="left-menu" data-menu="knowledge-bases">
    <div class="mobile-nav section-list"></div><ul>
    <li class="menu-back-link">
            <a href="https://docs.digitalocean.com/products/" class="contrast">
                <span class="menuText">Product Home</span>
            </a>
        </li><li><a href="/products/knowledge-bases/" class="contrast"><img src="/images/icons/knowledge-bases.ebabd81540283b9f8553f8c941f599c08f84136fa6f3b4e509be91f204a65245.svg" integrity="sha256-66vYFUAoO5&#43;FU/jJQfWZwI&#43;EE2&#43;m87TlCb6R8gSmUkU="><span class="menuText">Knowledge Bases</span></a>

</li>

<li><a href="/products/knowledge-bases/getting-started/" class="contrast has-fa" data-pdocs-menu-post="&#xf078"><span class="menuText">Getting Started</span></a>
<ul>
    <li><a href="/products/knowledge-bases/getting-started/quickstart/" class="contrast"><span class="menuText">Quickstart</span></a>

</li>


        <li><a href="/products/knowledge-bases/getting-started/data-services-use-rag-playground/" class="contrast"><span class="menuText">Use RAG Playground</span></a>

</li>


        </ul>
    
</li>


        <li><a href="/products/knowledge-bases/how-to/" class="contrast has-fa" data-pdocs-menu-post="&#xf078"><span class="menuText">How-Tos</span></a>
<ul>
    <li><a href="/products/knowledge-bases/how-to/create/" class="primary active"><span class="menuText">Create Knowledge Bases</span></a>

</li>

<li><a href="/products/knowledge-bases/how-to/destroy/" class="contrast"><span class="menuText">Destroy Knowledge Bases</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/test-knowledge-bases/" class="contrast"><span class="menuText">Test Knowledge Bases</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/edit-knowledge-bases/" class="contrast"><span class="menuText">Edit Knowledge Bases</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/manage-data-sources/" class="contrast"><span class="menuText">Manage Data Sources</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/index-data-sources/" class="contrast"><span class="menuText">Index Data Sources</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/view-indexing-jobs/" class="contrast"><span class="menuText">View Indexing Job Logs</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/test-knowledge-base-retrieval/" class="contrast"><span class="menuText">Test Knowledge Base Data Retrieval</span></a>

</li>


        </ul>
    
</li>

<li><a href="/products/knowledge-bases/reference/" class="contrast has-fa" data-pdocs-menu-post="&#xf078"><span class="menuText">Reference</span></a>
<ul>
    <li><a href="/reference/doctl/reference/gradient/knowledge-base/" class="contrast"><span class="menuText">doctl CLI Reference</span></a>

</li>


        <li><a href="/reference/mcp/" class="contrast"><span class="menuText">MCP Reference</span></a>

</li>


        <li><a href="/products/knowledge-bases/reference/data-services-chunking-strategies/" class="contrast"><span class="menuText">Chunking Parameters</span></a>

</li>


        </ul>
    
</li>


        <li><a href="/products/knowledge-bases/concepts/" class="contrast has-fa" data-pdocs-menu-post="&#xf078"><span class="menuText">Concepts</span></a>
<ul>
    <li><a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/" class="contrast"><span class="menuText">Chunking Best Practices</span></a>

</li>


        <li><a href="/products/knowledge-bases/concepts/data-services-system-instructions/" class="contrast"><span class="menuText">System Instructions Best Practices</span></a>

</li>


        <li><a href="/products/knowledge-bases/concepts/data-services-retrieval/" class="contrast"><span class="menuText">Retrieval Best Practices</span></a>

</li>


        </ul>
    
</li>


        <li><a href="/products/knowledge-bases/details/" class="contrast has-fa" data-pdocs-menu-post="&#xf078"><span class="menuText">Details</span></a>
<ul>
    <li><a href="/products/knowledge-bases/details/features/" class="contrast"><span class="menuText">Features</span></a>

</li>


        <li><a href="/products/knowledge-bases/details/pricing/" class="contrast"><span class="menuText">Pricing</span></a>

</li>


        <li><a href="/products/knowledge-bases/details/availability/" class="contrast"><span class="menuText">Availability</span></a>

</li>


        <li><a href="/products/knowledge-bases/details/limits/" class="contrast"><span class="menuText">Limits</span></a>

</li>


        <li><a href="/products/knowledge-bases/details/knowledge-base-models/" class="contrast"><span class="menuText">Available Models</span></a>

</li>


        <li><a href="/products/knowledge-bases/details/website-crawler/" class="contrast"><span class="menuText">Website Crawler</span></a>

</li>


        <li><a href="/products/inference/details/model-support-policy/" class="contrast"><span class="menuText">Model Support Policy</span></a>

</li>


        </ul>
    
</li>


        </ul>
</nav>
<script>



(function() {
    var menu = document.getElementById('left-menu');
    if (!menu) return;

    
    var key = 'pdocs-left-menu-scroll-' + (menu.dataset.menu || '');
    var saved = sessionStorage.getItem(key);
    if (saved) {
        menu.scrollTop = parseInt(saved, 10);
    }

    var active = menu.querySelector('a.active');
    if (active) {
        var mr = menu.getBoundingClientRect();
        var ar = active.getBoundingClientRect();
        if (ar.top < mr.top || ar.bottom > mr.bottom) {
            active.scrollIntoView({ block: 'center' });
        }
    }
})();
</script>
</aside>

        <main id="content">
            <div class="pico before-content">

<nav id="breadcrumbs" aria-label="breadcrumb">
<ul itemscope itemtype="https://schema.org/BreadcrumbList"><li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem"><a itemscope itemtype="https://schema.org/WebPage" itemprop="item" 
            href="/products/knowledge-bases/how-to/" itemid="/products/knowledge-bases/how-to/"
        >
            <span itemprop="name">How-Tos</span>
        </a><meta itemprop="position" content="1" />
    </li><li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem"><span itemprop="name">Create Knowledge Bases</span><meta itemprop="position" content="2" />
</li>
</ul>
</nav>
<div class="feedback">
    <span>
        <button onclick="thumbRatingClicked(this, 'Page Rating','2026-04-15 00:00:00 \u002b0000 UTC', 1);">
            <i class="fa-solid fa-thumbs-up" ></i>
        </button>
        <button onclick="thumbRatingClicked(this, 'Page Rating','2026-04-15 00:00:00 \u002b0000 UTC', 0);">
            <i class="fa-solid fa-thumbs-down" ></i>
        </button>
    </span>
    <span><a href="https://ideas.digitalocean.com/documentation">Give Feedback</a>
    </span>
</div>
</div>

            <section><blockquote class="agent-docs-directive" style="display:none">
  <p><strong>For AI agents:</strong> The documentation index is at <a href="https://docs.digitalocean.com/llms.txt">https://docs.digitalocean.com/llms.txt</a>. Markdown versions of pages use the same URL with <code>index.html.md</code> in place of the HTML page (for example, append <code>index.html.md</code> to the directory path instead of opening the HTML document).</p>
</blockquote>

                <hgroup id="content-header">
                    <h1>How to Create DigitalOcean Knowledge Bases</h1><p>Validated on 15 Apr 2026 • Last edited on 8 May 2026</p>
<p id="product-summary">DigitalOcean Knowledge Bases let you store, index, and retrieve data from private files, websites, Spaces buckets, and other sources to power retrieval-augmented generation with your own content.</p></hgroup>

                <div class="md-tools">
    <a href="#" class="page-tool copy-text has-fa" data-copy-url="/products/knowledge-bases/how-to/create/index.html.md" aria-label="Copy page as Markdown">
        <i class="fa-regular fa-clipboard"></i> Copy page as Markdown
    </a>
    <a href="/products/knowledge-bases/how-to/create/index.html.md" class="page-tool view-markdown has-fa" target="_blank" rel="noopener" aria-label="View page as Markdown">
        <i class="fa-regular fa-file-lines"></i> View page as Markdown <i class="fa-solid fa-arrow-up-right-from-square"></i>
    </a>
</div>
<p>A knowledge base stores data sources (such as local file uploads, <a href="/products/spaces/">DigitalOcean Spaces buckets or folders</a>, public seed or sitemap URLs, <a href="https://www.dropbox.com">Dropbox</a> folders, and <a href="https://aws.amazon.com/s3/">Amazon S3 buckets</a>), that AI agents can use to answer questions with retrieval-augmented generation (RAG). RAG helps agents provide more accurate, current, and domain-specific responses.</p>
<p>When you create a knowledge base, your data is immediately indexed by converting the content into vector embeddings using an embeddings model. These embeddings capture the meaning of your content and are stored in a <a href="/products/databases/opensearch/">Managed OpenSearch database</a>, which you can <a href="/products/databases/opensearch/how-to/resize/">scale to improve performance</a>. The embeddings model determines token limits, chunk size ranges, and whether size estimates are available when you <a href="/products/knowledge-bases/how-to/view-indexing-jobs/">download the CSV for the indexing job</a>.</p>
<article class="notice notice-note">
    <header>Note</header>
    Size estimates in the CSV are based on total data size, not extractable text, and are available only for local uploads and Spaces buckets. Other sources show <code>estimate unavailable</code>.
</article>

<p>Each knowledge base requires at least one data source, and <a href="/products/knowledge-bases/how-to/manage-data-sources/#add-data-control">you can add or remove sources after creation</a>.</p>
<h2 id="create-control">Create a Knowledge Base Using the Control Panel
    <a href="#create-control" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#create-control');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>To create a knowledge base, go to the <a href="https://cloud.digitalocean.com/">DigitalOcean Control Panel</a>, in the left menu, click <strong>DATA SERVICES</strong>, and then click <strong>Knowledge Bases</strong>.</p>
<p>Then, in the top-right, click <strong>Create Knowledge Base</strong> to open the <strong>Create a knowledge base</strong> page.</p>
<h3 id="create-model">Choose Your Embeddings Model
    <a href="#create-model" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#create-model');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Under the <strong>Add data</strong> step, click the <strong>Choose your embeddings model</strong> dropdown list, and choose an embeddings model. You can&rsquo;t change the model after creating your knowledge base.</p>
<p>An embeddings model converts your data into vector embeddings which are stored in an <a href="/products/databases/opensearch/">OpenSearch database</a>. We offer <a href="/products/knowledge-bases/details/knowledge-base-models/#embeddings-models">multiple embeddings models</a> for different use cases. The <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">indexing costs</a> depend on the selected model and the size of your data.</p>
<p>To understand your indexing costs, click <strong>How much will I pay for an indexing job?</strong>. This opens the <strong>Estimating index job costs</strong> window, which shows estimated indexing costs by embeddings model token rate and dataset size. Larger datasets cost more to index, and you only pay for successfully indexed data. Final costs may vary. For details, see <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">embeddings model pricing</a>.</p>
<h3 id="config-reranking">Configure Reranking
    <a href="#config-reranking" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#config-reranking');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>You can optionally enable reranking for retrieval results when you create the knowledge base. Reranking reorders results after the initial search so the most relevant chunks are more likely to appear first and be used in generated responses.</p>
<p>If reranking is enabled, reranking tokens are billed separately from vectorizing retrieval queries. For more information, see <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">knowledge base pricing</a>.</p>
<p>Under the <strong>Choose your reranking model</strong> section, click the <strong>Reranking model (optional)</strong> dropdown list, and then select a reranking model. Choose a reranking model based on the relevance quality you need, your latency requirements, and <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">your cost considerations</a>. You can&rsquo;t change the reranking model after enabling reranking. To see the reranking models, see our <a href="/products/knowledge-bases/details/knowledge-base-models/#reranking-models">available reranking models</a>.</p>
<p>If reranking is enabled, retrieval results show that reranking is active, along with the model name and per-token pricing. Reranking applies to all retrieval requests and incurs charges on each request.</p>
<h3 id="create-add-data">Add Data Sources
    <a href="#create-add-data" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#create-add-data');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>You can add multiple types of data sources and include as many as needed. To save processing time and cost, organize your files in dedicated <a href="/products/spaces/">Spaces buckets</a>, specific folders, or local storage containing only relevant files.</p>
<p>To avoid delays, we recommend uploading fewer than 100 files at a time, each under 2 GB. For larger uploads, use the <a href="/products/spaces/reference/">DigitalOcean API</a>. If uploads continue to stall, <a href="https://cloudsupport.digitalocean.com">contact support</a>.</p>
<p>In the <strong>Add data sources</strong> section, under the <strong>Select data sources to index</strong> sub-section, select the type of data you want to add.</p>
<p>Knowledge bases support the following text-based file formats: <code>.csv</code>, <code>.eml</code>, <code>.epub</code>, <code>.xls</code>, <code>.xlsx</code>, <code>.html</code>, <code>.md</code>, <code>.odt</code>, <code>.pdf</code>, <code>.txt</code>, <code>.rst</code>, <code>.rtf</code>, <code>.tsv</code>, <code>.doc</code>, <code>.docx</code>, <code>.xml</code>, <code>.json</code>, and <code>.jsonl</code>. When supported files contain embedded media, such as images or SVGs, we also attempt to index that content.</p>
<p>You can add any of the following data sources:</p>
<div class="tabs">
    
<input type="radio" name="data-sources" id="data-sources-file-upload" checked>
<label for="data-sources-file-upload">File Upload</label>
<div class="tab-content"><p>To upload files, click <strong>Upload a file</strong> to open the <strong>Select files to upload</strong> window.</p>
<p>For performance and reliability, we recommend uploading files no larger than 2 GB and uploading fewer than 100 files at a time.</p>
<p>Under the <strong>Choose Files</strong> section, either click <strong>Upload</strong>, or drag-and-drop at least one file.</p>
<p>If you want to add more files, on the bottom right, click <strong>Upload more files</strong>.</p>
<p>If you want to remove a file, on the right of it, click the trash icon.</p>
</div>

<input type="radio" name="data-sources" id="data-sources-spaces-bucket-or-folder">
<label for="data-sources-spaces-bucket-or-folder">Spaces Bucket or Folder</label>
<div class="tab-content"><p>To add a <a href="/products/spaces/">Spaces bucket or folder</a>, click <strong>Pull from a Spaces bucket or folder</strong> to open the <strong>Select Spaces bucket or folder</strong> window.</p>
<p>We can index all supported file formats in selected buckets and folders, regardless of privacy settings.</p>
<p>Then, either choose at least one bucket or folder you want to index, or on the left of a bucket, click <strong>+</strong> to expand its contents, and then select specific folders. For optimal performance and indexing quality, we recommend using five or fewer buckets and uploading only indexing data to your buckets.</p>
</div>

<input type="radio" name="data-sources" id="data-sources-web-or-site-map-url">
<label for="data-sources-web-or-site-map-url">Web or Site Map URL</label>
<div class="tab-content"><article class="notice notice-note">
    <header>Note</header>
    <p>When you specify a website URL as a data source for your knowledge base, DigitalOcean uses a custom agent named <code>DigitalOceanGradientAICrawler/1.0</code> to index the website content. The crawler indexes up to 5,500 pages and skips inaccessible or disallowed links to prevent excessively large indexing jobs.</p>
<p>Depending on the behavior you select, the crawler follows HTML links on the site, indexes text and certain image types, and ignores videos and navigation links. It respects the website&rsquo;s <code>robots.txt</code> rules, including any <code>Disallow</code> directives or the wildcard <code>*</code>.</p>
</article>
<p>To add a URL for web crawling, click <strong>Add a web or site map URL</strong>. You can then choose to specify a <a href="#seed-url"><strong>Seed URL</strong></a> or a <a href="#site-map-url"><strong>Site map URL</strong></a>.</p>
<h3 id="seed-url">Specify Seed URL
    <a href="#seed-url" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#seed-url');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Specifying a seed URL crawls only the seed URL and linked pages within the same path, domain, or subdomains.</p>
<p>To specify a seed URL, click <strong>Seed URL</strong>, and then in the <strong>Seed URL</strong> field, enter the public URL you want to crawl.</p>
<p>Under the <strong>Crawling rules</strong> section, select the crawl scope (from most narrow to most broad):</p>
<ul>
<li><strong>Scoped</strong> crawls only the seed URL.</li>
<li><strong>URL and all linked pages in path</strong> crawls the seed URL and all pages within the same path.</li>
<li><strong>URL and all linked pages in domain</strong> crawls all pages in the same domain.</li>
<li><strong>Subdomains</strong> crawls the domain and all its subdomains.</li>
</ul>
<p>Click the <strong>Index embedded media</strong> option to index supported images and other media encountered during the crawl.</p>
<p>Click the <strong>Include headers and footers navigation links</strong> option to include each page&rsquo;s header and footer content, such as links in them.</p>
<h3 id="site-map-url">Specify Site Map URL
    <a href="#site-map-url" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#site-map-url');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Specifying the site map URL crawls only URLs listed in the site map.</p>
<p>To crawl other URLs, use the <a href="#specify-seed-url"><strong>Seed URL</strong></a> option, or add another web crawling data source.</p>
<p>To specify a site map URL, click <strong>Sitemap URL</strong>, and then in the <strong>Sitemap URL</strong> field, enter the URL you want to crawl. For example, <code>docs.digitalocean.com/sitemap.xml</code>.</p>
<p>The site map URL must be in <code>.xml</code> format where you can identify a specific list of URLs to crawl. You can use a site map URL to add scoped URLs all at once instead of adding them individually, or choosing a crawling rule for a seed URL.</p>
<p>Click the <strong>Index embedded media</strong> option to index supported images and other media encountered during the crawl.</p>
<p>Click the <strong>Include headers and footers navigation links</strong> option to include each page&rsquo;s header and footer content, such as links in them.</p>
</div>

<input type="radio" name="data-sources" id="data-sources-dropbox-folder">
<label for="data-sources-dropbox-folder">Dropbox Folder</label>
<div class="tab-content"><p>If you haven&rsquo;t connected your Dropbox account, on the right of the <strong>Pull from a Dropbox folder</strong> option, click <strong>Connect account</strong> to first log in to your Dropbox account and authorize the connection.</p>
<p>To add a <a href="https://www.dropbox.com">Dropbox</a> folder, click <strong>Pull from a Dropbox folder</strong>, and then choose at least one folder you want to index, or on the left of a folder, click <strong>+</strong> to expand its contents and select specific folders.</p>
</div>

<input type="radio" name="data-sources" id="data-sources-amazon-s3-bucket-or-folder">
<label for="data-sources-amazon-s3-bucket-or-folder">Amazon S3 Bucket or Folder</label>
<div class="tab-content"><p>To add an Amazon S3 bucket or folder, click <strong>Pull from an AWS S3 bucket folder</strong>.</p>
<p>In the <strong><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html">Access Key ID</a></strong> field, enter the IAM access key ID for your S3 bucket or folder.</p>
<p>In the <strong>Secret Key</strong> field, enter the secret key associated with your access key ID.</p>
<p>In the <strong>Bucket Name</strong> field, enter the name of the S3 bucket to index.</p>
<p>In the <strong>Region</strong> field, enter the AWS region where your S3 bucket folder is located, such as <code>us-east-1</code> or <code>eu-west-1</code>.</p>
<p>On the right of the <strong>Region</strong> field, click <strong>+</strong> to add the S3 bucket.</p>
</div>


</div>

<p>If you want to control how the data source is split into chunks during indexing, click <strong>Advanced Options</strong> to <a href="/products/knowledge-bases/how-to/create/#config-chunk">configure its chunking strategy</a>. By default, all data sources use section-based chunking. For more information about chunking strategies, see our <a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/">chunking strategy best practices</a>.</p>
<p>Then, click <strong>Add selected data source</strong>.</p>
<p>After adding your data source, <a href="#add-control">add another data source if you want</a>, and then in the top-right, review the data sources you&rsquo;ve added with their data source type, estimated size, and configuration (such as, chunking configuration).</p>
<article class="notice notice-note">
    <header>Note</header>
    Size estimates are available only for sources with known values, such as Spaces buckets and uploaded files. For other sources, the size appears after the initial indexing job completes.
</article>

<p>If one of your data sources fails to be added, click the data source method you chose for that data source, and then on the right of the failed file, bucket, folder or URL, click the trash icon, and then <a href="#add-data-control">try again</a>. If it fails again, <a href="https://cloudsupport.digitalocean.com">contact support</a>.</p>
<p>After adding all your data sources and reviewing them, click <strong>Next step: Configure database</strong>, or <a href="#config-chunk">configure chunking strategies for your data sources</a></p>
<h3 id="config-chunk">Configure Chunking Strategy
    <a href="#config-chunk" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#config-chunk');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Chunking controls how each data source is split before embedding and indexing the source into your knowledge base. Data sources use section-based chunking by default, and you can use different strategies in the same knowledge base by adding content as separate data sources.</p>
<p>Chunking strategies depend on the <a href="/products/inference/details/models/#embeddings-model">selected embeddings model</a>. Chunk sizes must stay within the model&rsquo;s token window and be at least approximately 100 tokens. For insights on which strategy to choose and configuration setup, see our <a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/">chunking best practices</a> and the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/">chunking parameters reference</a>.</p>
<p>To configure chunking after selecting your data source, at the bottom of the data source&rsquo;s selection window, click <strong>Advanced Options</strong> to open the <strong>Chunking strategy</strong> section.</p>
<p>Under the <strong>Select a chunking strategy for this data source</strong> sub-section, click the strategy you want to use, and then configure its parameters.</p>
<p>You can choose one of the following strategies:</p>
<div class="overflow-auto">
<table>
  <thead>
      <tr>
          <th style="text-align: left">Chunking strategy</th>
          <th style="text-align: left">How it works</th>
          <th style="text-align: left">Best For</th>
          <th style="text-align: left">Configuration</th>
      </tr>
  </thead>
  <tbody>
      <tr>
          <td style="text-align: left"><strong>Section-based chunking (default)</strong></td>
          <td style="text-align: left">Splits content using structural elements such as headings, paragraphs, tables, and lists.</td>
          <td style="text-align: left">Structured documents where preserving document layout matters. This strategy is fast and low cost.</td>
          <td style="text-align: left">Use the <strong>Maximum chunk size</strong> slider to set the maximum number of tokens per chunk. The value must stay within the embeddings model&rsquo;s limits.</td>
      </tr>
      <tr>
          <td style="text-align: left"><strong>Semantic chunking</strong></td>
          <td style="text-align: left">Groups text by meaning using embeddings.</td>
          <td style="text-align: left">Content where related ideas should stay together even when structure is limited. This strategy is slower and higher cost because it uses embeddings for both chunk detection and final embedding.</td>
          <td style="text-align: left">Use the <strong>Similarity threshold</strong> field to set how similar sentences must be to group together. Lower values create larger sentence groups. Use the <strong>Maximum chunk size</strong> slider to set the maximum number of tokens per chunk.</td>
      </tr>
      <tr>
          <td style="text-align: left"><strong>Hierarchical chunking</strong></td>
          <td style="text-align: left">Creates parent chunks for broader context and child chunks for retrieval. Retrieval returns the child chunk first, then includes the parent chunk for additional context.</td>
          <td style="text-align: left">Documents where smaller passages need surrounding context.</td>
          <td style="text-align: left">Use the <strong>Maximum parent chunk size</strong> slider to set the maximum number of tokens in each parent chunk. Use the <strong>Maximum child chunk size</strong> slider to set the maximum number of tokens in each child chunk. Child chunks must be smaller than parent chunks.</td>
      </tr>
      <tr>
          <td style="text-align: left"><strong>Fixed-length chunking</strong></td>
          <td style="text-align: left">Splits text by token count and ignores formatting or structure.</td>
          <td style="text-align: left">Unstructured data such as logs, telemetry, or Optical Character Recognition (OCR).</td>
          <td style="text-align: left">Use the <strong>Maximum chunk size</strong> slider to set the maximum number of tokens per chunk. The value must stay within the embeddings model&rsquo;s limits.</td>
      </tr>
  </tbody>
</table>
</div>
<p>If you decide to <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#test-chunk">change chunking strategies after creating your knowledge base</a>, this requires re-indexing, which consumes additional tokens.</p>
<p>After setting up your chunking configuration your data source, click <strong>Add selected data source</strong>, and <a href="#chunk">repeat for another data source</a>, if necessary. Then, click <strong>Next step: Configure database</strong>.</p>
<h3 id="choose-knowledge-base-name">Choose Knowledge Base Name
    <a href="#choose-knowledge-base-name" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#choose-knowledge-base-name');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>In the <strong>Configure database</strong> step, either keep the autogenerated name or choose a unique name using 3 to 63 characters, including only letters, numbers, dashes, and periods.</p>
<h3 id="opensearch-create">Choose Your OpenSearch Database
    <a href="#opensearch-create" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#opensearch-create');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Knowledge bases require an <a href="/products/databases/opensearch/">OpenSearch database</a> to store vector embeddings. On the top-right of the page, use the estimated sizes in your added data sources list to choose a database size. We recommend allocating at least twice the total estimated data size. Database size is based on <a href="/products/databases/opensearch/details/pricing/">OpenSearch pricing</a>.</p>
<p>If you want to remove a data source, click <strong>Edit data sources</strong>, which takes you back to the <strong>Add data</strong> step, and then under the <strong>Add data sources</strong> section, select the data source method with the data you want to remove, and then click the trash icon next to the data.</p>
<p>In the <strong>Where should your knowledge base live?</strong> section, under the <strong>OpenSearch database options</strong> sub-section, select either <strong>Use existing</strong> to connect to an existing OpenSearch database or <strong>Create new</strong> to provision a new one.</p>
<div class="tabs">
    
<input type="radio" name="database" id="database-use-existing-opensearch-database" checked>
<label for="database-use-existing-opensearch-database">Use Existing OpenSearch Database</label>
<div class="tab-content"><p>If you choose <strong>Use existing</strong>, click the <strong>Select an OpenSearch database</strong> dropdown list, and then select the database you want to use. If it already contains data, it may limit how much new data you can index. You only pay for successfully indexed data.</p>
</div>

<input type="radio" name="database" id="database-create-a-new-opensearch-database">
<label for="database-create-a-new-opensearch-database">Create a New OpenSearch Database</label>
<div class="tab-content"><p>Creating a new database automatically sets the smallest size that fits your data. We recommend allocating about twice the size of your total estimated data source size to efficiently store embeddings.</p>
<p>If you choose <strong>Create new</strong>, under the <strong>Choose a datacenter region</strong> section, either keep the default datacenter region, or click the <strong>Additional datacenter regions</strong> dropdown list to choose a different one.</p>
<p>If you want to attach the knowledge base to <a href="/products/inference/">agents</a>, choose the same region as your agents to reduce latency. Most Agent Platform infrastructure is in TOR1, so we recommend the default region.</p>
<p>Under the <strong>VPC Network</strong> section, choose the VPC where your OpenSearch database is created.</p>
<p>Your VPC network determines which resources (such as agents or other applications) can access it. We recommend selecting the same VPC as those resources, so they can connect securely over a private network.</p>
</div>


</div>

<p>Afterwards, click <strong>Next step: Review and create</strong>.</p>
<h3 id="finalize-details">Finalize Details
    <a href="#finalize-details" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#finalize-details');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>In the <strong>Review</strong> step, under the <strong>Final Details</strong> section, click the <strong>Select a project</strong> dropdown list to choose the project you want your knowledge base stored in.</p>
<p>In the <strong>Tags</strong> field, add tags to help organize and filter your knowledge base. Tags can include letters, numbers, colons, dashes, and underscores. Choose a tag name, then press <code>ENTER</code> or <code>SPACEBAR</code> to add it. Use the arrow keys to navigate and the <code>BACKSPACE</code> key to remove tags.</p>
<p>Under the <strong>Review</strong> section, use the configuration sub-sections to confirm your embeddings model and token cost, selected data sources and estimated total size, and OpenSearch database specs and price. Existing databases don&rsquo;t add new database charges.</p>
<p>To change a configuration, click <strong>Edit</strong> next to the sub-section you want to update, and then make your changes in its respective step.</p>
<p>After finalizing and reviewing your knowledge base setup, click <strong>Create knowledge base</strong> (or <strong>Create Knowledge Base and database</strong>).</p>
<h3 id="provisioning-your-knowledge-base">Provisioning Your Knowledge Base
    <a href="#provisioning-your-knowledge-base" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#provisioning-your-knowledge-base');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>After creating your knowledge base, it appears in the <a href="https://cloud.digitalocean.com/knowledge-bases"><strong>Knowledge bases</strong> page</a> and immediately begins provisioning. Provisioning typically takes five minutes or longer as the process embeds and indexes your data sources.</p>
<p>After provisioning completes, click your knowledge base to view its <strong>Overview</strong> section. Under the <strong>LATEST INDEXING DETAILS</strong> sub-section view a summary of the indexing results, including final costs. You can download a CSV file of this index job in the knowledge base&rsquo;s <a href="/products/knowledge-bases/how-to/view-indexing-jobs/"><strong>Activity</strong> tab</a>.</p>
<p>If indexing takes longer than expected, let the indexing job continue running until it either completes or fails. If it fails, <a href="/products/knowledge-bases/how-to/view-indexing-jobs/">check the <strong>Activity</strong> tab for detailed logs to understand what went wrong</a> (for example, failed or skipped files).</p>
<p>After reviewing the indexing job logs and fixing any issues, on the right of the log, click <strong>Re-run</strong> to restart indexing. If problems persist, <a href="https://cloudsupport.digitalocean.com">contact support</a>.</p>
<p>If you added a seed or site map URL as a data source, verify web crawling is indexed successfully by re-adding the <a href="#seed-url">same seed</a> or <a href="#site-map-url">sitemap URL</a> as a new data source. If the <a href="/products/knowledge-bases/how-to/view-indexing-jobs/">indexing job results</a> of the duplicated data source shows zero tokens, the original crawl indexed all content, and you can <a href="/products/knowledge-bases/how-to/manage-data-sources/#delete-data-control">delete the duplicate</a>.</p>
<p>To keep your data sources up to date automatically without manual re-ingest, we recommend also <a href="/products/knowledge-bases/how-to/index-data-sources/#schedule-control">setting up scheduled indexing</a>.</p>
<h2 id="create-api">Create a Knowledge Base via the API
    <a href="#create-api" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#create-api');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>To create a knowledge base via the DigitalOcean API, provide a name, an <a href="/products/knowledge-bases/details/knowledge-base-models/#embeddings-models">embeddings model</a>, a project ID, and a datacenter region.</p>
<p>You can also specify the ID of an existing OpenSearch database or a chunking strategy. If you don&rsquo;t provide a database, we create one and size one for you automatically.</p>
<p>You can configure your chunking strategy for a data source when creating your knowledge base with the following optional fields:</p>
<ul>
<li><strong><code>chunking_algorithm</code></strong>: The chunking strategy (<code>section</code>, <code>semantic</code>, <code>hierarchical</code>, or <code>fixed</code>).</li>
<li><strong><code>chunking_options</code></strong>: A configuration object containing parameters such as <code>max_chunk_size</code>, <code>semantic_threshold</code>, <code>parent_chunk_size</code>, or <code>child_chunk_size</code>.</li>
</ul>
<p>Chunking is applied per data source. Updating chunking settings triggers re-indexing, which consumes tokens. For details and recommendations, see our <a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/">chunking best practices</a> and <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/">chunking parameters reference</a>.</p>
<p>If you don&rsquo;t configure a chunking strategy for a data source, the knowledge base uses section-based chunking (<code>section</code>) by default.</p>
<p>To list available embeddings models and their IDs, call the <a href="/reference/api/reference/gradientai-platform/#genai_list_models"><code>/v2/gen-ai/models</code> endpoint</a> with the <code>usecases</code> query parameter.</p>
<details class="expand">
    <summary role="button" class="outline contrast" onclick="&#34;logToLooker(&#39;Expand API Instructions&#39;,\&#34;Create a Knowledge Base\&#34;,0)&#34;">How to Create a Knowledge Base Using the DigitalOcean API</summary><p><a href="https://docs.digitalocean.com/reference/api/create-personal-access-token/">Create a personal access token</a> and save it for use with the API.</p>
<h3 id="create-a-knowledge-base-curl">cURL
    <a href="#create-a-knowledge-base-curl" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#create-a-knowledge-base-curl');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Send a POST request to <a href="https://docs.digitalocean.com/reference/api/reference/gradientai-platform/#genai_create_knowledge_base"><code>https://api.digitalocean.com/v2/gen-ai/knowledge_bases</code></a>.</p>
<p>Using cURL:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-shell" data-lang="shell"><span class="line"><span class="cl">curl -X POST <span class="se">\
</span></span></span><span class="line"><span class="cl">  -H <span class="s2">&#34;Content-Type: application/json&#34;</span>  <span class="se">\
</span></span></span><span class="line"><span class="cl">  -H <span class="s2">&#34;Authorization: Bearer </span><span class="nv">$DIGITALOCEAN_TOKEN</span><span class="s2">&#34;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">  <span class="s2">&#34;https://api.digitalocean.com/v2/gen-ai/knowledge_bases&#34;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">  -d <span class="s1">&#39;{
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;name&#34;: &#34;kb-api-create&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;embedding_model_uuid&#34;: &#34;05700391-7aa8-11ef-bf8f-4e013e2ddde4&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;project_id&#34;: &#34;37455431-84bd-4fa2-94cf-e8486f8f8c5e&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;tags&#34;: [
</span></span></span><span class="line"><span class="cl"><span class="s1">      &#34;tag1&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">    ],
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;database_id&#34;: &#34;abf1055a-745d-4c24-a1db-1959ea819264&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;datasources&#34;: [
</span></span></span><span class="line"><span class="cl"><span class="s1">      {
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;spaces_data_source&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">              &#34;bucket_name&#34;: &#34;test-public-gen-ai&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">              &#34;region&#34;: &#34;tor1&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">            },
</span></span></span><span class="line"><span class="cl"><span class="s1">            &#34;chunking_algorithm&#34;: &#34;CHUNKING_ALGORITHM_HIERARCHICAL&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">            &#34;chunking_options&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">              &#34;parent_chunk_size&#34;: 1000,
</span></span></span><span class="line"><span class="cl"><span class="s1">              &#34;child_chunk_size&#34;: 350
</span></span></span><span class="line"><span class="cl"><span class="s1">            }
</span></span></span><span class="line"><span class="cl"><span class="s1">      },
</span></span></span><span class="line"><span class="cl"><span class="s1">      {
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;web_crawler_data_source&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;base_url&#34;: &#34;https://example.com&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;crawling_option&#34;: &#34;SCOPED&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;embed_media&#34;: false,
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;exclude_tags&#34;: [&#34;nav&#34;,&#34;footer&#34;,&#34;header&#34;,&#34;aside&#34;,&#34;script&#34;,&#34;style&#34;,&#34;form&#34;,&#34;iframe&#34;, &#34;noscript&#34;]
</span></span></span><span class="line"><span class="cl"><span class="s1">        },
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;chunking_algorithm&#34;: &#34;CHUNKING_ALGORITHM_SEMANTIC&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;chunking_options&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;max_chunk_size&#34;: 500,
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;semantic_threshold&#34;: 0.6
</span></span></span><span class="line"><span class="cl"><span class="s1">        }
</span></span></span><span class="line"><span class="cl"><span class="s1">      },
</span></span></span><span class="line"><span class="cl"><span class="s1">      {
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;spaces_data_source&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">            &#34;bucket_name&#34;: &#34;test-public-gen-ai-2&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">            &#34;region&#34;: &#34;tor1&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">          },
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;chunking_algorithm&#34;: &#34;CHUNKING_ALGORITHM_FIXED_LENGTH&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">          &#34;chunking_options&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">            &#34;max_chunk_size&#34;: 400
</span></span></span><span class="line"><span class="cl"><span class="s1">          }
</span></span></span><span class="line"><span class="cl"><span class="s1">      },
</span></span></span><span class="line"><span class="cl"><span class="s1">    ],
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;region&#34;: &#34;tor1&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;vpc_uuid&#34;: &#34;f7176e0b-8c5e-4e32-948e-79327e56225a&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;reranking_config&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">      &#34;enabled&#34;: true,
</span></span></span><span class="line"><span class="cl"><span class="s1">      &#34;model&#34;: &#34;bge-reranker-v2-m3&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">    }
</span></span></span><span class="line"><span class="cl"><span class="s1">  }&#39;</span></span></span></code></pre></div>
</details>

<p>After creating your knowledge base, indexing begins automatically. You can <a href="/reference/api/reference/gradientai-platform/#genai_list_knowledge_bases">list all knowledge bases</a>, <a href="/reference/api/reference/gradientai-platform/#genai_get_knowledge_base">view a knowledge base</a>, or <a href="/reference/api/reference/gradientai-platform/#genai_update_knowledge_base">update one</a>.</p>
<p>To add another data source, use the <a href="/reference/api/reference/gradientai-platform/#genai_create_knowledge_base_data_source">Data Sources endpoint</a>.</p>
<p>To retrieve metadata for embeddings models, use the <a href="/reference/api/reference/gradientai-platform/#genai_list_models">List Models endpoint</a>.</p>
</section>
        </main>

        <aside id="right-nav"><div id="right-menu">
                <p>In this article...</p><nav id="TableOfContents">
  <ul>
    <li><a href="#create-control">Create a Knowledge Base Using the Control Panel</a>
      <ul>
        <li><a href="#create-model">Choose Your Embeddings Model</a></li>
        <li><a href="#config-reranking">Configure Reranking</a></li>
        <li><a href="#create-add-data">Add Data Sources</a></li>
        <li><a href="#config-chunk">Configure Chunking Strategy</a></li>
        <li><a href="#choose-knowledge-base-name">Choose Knowledge Base Name</a></li>
        <li><a href="#opensearch-create">Choose Your OpenSearch Database</a></li>
        <li><a href="#finalize-details">Finalize Details</a></li>
        <li><a href="#provisioning-your-knowledge-base">Provisioning Your Knowledge Base</a></li>
      </ul>
    </li>
    <li><a href="#create-api">Create a Knowledge Base via the API</a></li>
  </ul>
</nav>
            </div></aside>

        <footer id="footer" class="pico">
            <div id="footer-top" class="footer-section"><div>
        <h5>Company</h5>
        <ul><li><a href="https://www.digitalocean.com/about">About</a></li><li><a href="https://www.digitalocean.com/careers">Careers</a></li><li><a href="https://www.digitalocean.com/blog">Blog</a></li></ul>
    </div><div>
        <h5>Docs</h5>
        <ul><li><a href="https://docs.digitalocean.com">Docs Home</a></li><li><a href="https://docs.digitalocean.com/reference/api">API Reference</a></li><li><a href="https://docs.digitalocean.com/reference/doctl">CLI Reference</a></li><li><a href="https://docs.digitalocean.com/release-notes">Release Notes</a></li><li><a href="https://docs.digitalocean.com/llms.txt">llms.txt</a></li><li><a href="https://www.digitalocean.com/trust">Trust Platform</a></li></ul>
    </div><div>
        <h5>Community</h5>
        <ul><li><a href="https://www.digitalocean.com/community/tutorials">Tutorials</a></li><li><a href="https://www.digitalocean.com/community/questions">Q&amp;A</a></li><li><a href="https://www.digitalocean.com/community/pages/write-for-digitalocean">Write for DOnations</a></li><li><a href="https://www.digitalocean.com/currents">Currents Research</a></li><li><a href="https://www.digitalocean.com/legal">Legal</a></li><li><a href="https://www.digitalocean.com/community/pages/code-of-conduct">Code of Conduct</a></li></ul>
    </div><div>
        <h5>Support</h5>
        <ul><li><a href="/support">Support Center</a></li><li><a href="https://www.digitalocean.com/company/contact/abuse">Report Abuse</a></li></ul>
    </div></div>

<hr>

<div id="footer-bottom" class="footer-section">
    <small class="copyright">© 2026 DigitalOcean, LLC. All rights reserved</small>

    <div><a href="https://x.com/digitalocean" class="social">
            <i class="fa-brands fa-x-twitter"></i>
        </a><a href="https://www.instagram.com/thedigitalocean" class="social">
            <i class="fa-brands fa-instagram"></i>
        </a><a href="https://www.facebook.com/DigitalOceanCloudHosting" class="social">
            <i class="fa-brands fa-facebook"></i>
        </a><a href="https://discord.gg/digitalocean" class="social">
            <i class="fa-brands fa-discord"></i>
        </a><a href="https://www.youtube.com/DigitalOcean" class="social">
            <i class="fa-brands fa-youtube"></i>
        </a><a href="https://www.linkedin.com/company/digitalocean" class="social">
            <i class="fa-brands fa-linkedin"></i>
        </a><a href="https://github.com/digitalocean" class="social">
            <i class="fa-brands fa-github"></i>
        </a></div>
</div>

        </footer>
    </div>

    
    


<script src="https://docs.digitalocean.com/js/bundle.min.48800681a0611dc81db32798ad80067b92bb6d58ada2a164f752962119994669c56abf020050faf79a28a814a25d36f1c1e8ab8c2e5f76a06e9573f86dc42000.js" integrity="sha512-SIAGgaBhHcgdsyeYrYAGe5K7bVitoqFk91KWIRmZRmnFar8CAFD695ooqBSiXTbxweirjC5fdqBulXP4bcQgAA=="></script>


<script src="https://assets.digitalocean.com/labs/search.js.gz" defer onload="init_algolia()"></script>
<div id="algolia_empty_state">
    <h3>We can&#39;t find any results for your search.</h3>
    <p>Try using different keywords or simplifying your search terms.</p>
</div>


<script async src="https://yxt72quk3m7tpemhea54qobd.agents.do-ai.run/static/chatbot/widget.js"
    data-agent-id="2d2d7649-d6e0-11f0-b074-4e013e2ddde4"
    data-chatbot-id="vJdL-kXYvZQL1Zc9inmdPyPavYK6vjeL"
    data-name="DigitalOcean Docs Agent"
    data-primary-color="#0069ff"
    data-secondary-color="#E5E8ED"
    data-button-background-color="#0061EB"
    data-starting-message="This is the DigitalOcean Docs AI, built with OpenAI GPT-4o. You can ask it questions such as `How do I create a Droplet?` or `How do I set up a domain?`

Responses may not always be accurate, but we’re continuously working to improve the experience. This AI does not connect to DigitalOcean’s support team. For support, visit our support page: https://do.co/support.

We’d also like to hear your feedback about your experience: https://do.co/ask-docs-feedback"
    data-logo="https://product-docs.nyc3.cdn.digitaloceanspaces.com/ai-agent-icon.svg"
></script>

    
</body>
</html>



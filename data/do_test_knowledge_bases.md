Title: Live Content

Description: Fetched live

Source: https://docs.digitalocean.com/products/knowledge-bases/how-to/test-knowledge-bases/

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
<meta name="color-scheme" content="light dark"><meta name="description" content="Test retrieval results, update chunking strategy, and use the Knowledge Base API to query knowledge base data.">

<meta name="generator" content="Hugo 0.161.1">

<meta name="google-site-verification" content="CAYPZwe7daX8KlYYZfB4VMjfT4g8Tqrrc4Q3g_wMvI8">

<meta name="og:site_name" content="DigitalOcean">
<meta name="og:type" content="article">

<meta name="twitter:site" content="DigitalOcean">
<meta name="twitter:creator" content="@DigitalOcean">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:url" content="https://docs.digitalocean.com/products/knowledge-bases/how-to/test-knowledge-bases/">

<link rel="canonical" href="https://docs.digitalocean.com/products/knowledge-bases/how-to/test-knowledge-bases/">
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
  "description": "Test retrieval results, update chunking strategy, and use the Knowledge Base API to query knowledge base data.",
  "headline": "How to Test DigitalOcean Knowledge Bases",
  "image": "https://www.digitalocean.com/_next/static/media/intro-to-cloud.d49bc5f7.jpeg",
  "inLanguage": "en",
  "keywords": "DigitalOcean, cloud computing",
  "mainEntityOfPage": {
    "@id": "https://docs.digitalocean.com/products/knowledge-bases/how-to/test-knowledge-bases/",
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
<title>How to Test DigitalOcean Knowledge Bases | DigitalOcean Documentation</title>

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
    <li><a href="/products/knowledge-bases/how-to/create/" class="contrast"><span class="menuText">Create Knowledge Bases</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/destroy/" class="contrast"><span class="menuText">Destroy Knowledge Bases</span></a>

</li>


        <li><a href="/products/knowledge-bases/how-to/test-knowledge-bases/" class="primary active"><span class="menuText">Test Knowledge Bases</span></a>

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
    </li><li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem"><span itemprop="name">Test Knowledge Bases</span><meta itemprop="position" content="2" />
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
                    <h1>How to Test DigitalOcean Knowledge Bases</h1><p>Validated on 15 Apr 2026 • Last edited on 8 May 2026</p>
<p id="product-summary">DigitalOcean Knowledge Bases let you store, index, and retrieve data from private files, websites, Spaces buckets, and other sources to power retrieval-augmented generation with your own content.</p></hgroup>

                <div class="md-tools">
    <a href="#" class="page-tool copy-text has-fa" data-copy-url="/products/knowledge-bases/how-to/test-knowledge-bases/index.html.md" aria-label="Copy page as Markdown">
        <i class="fa-regular fa-clipboard"></i> Copy page as Markdown
    </a>
    <a href="/products/knowledge-bases/how-to/test-knowledge-bases/index.html.md" class="page-tool view-markdown has-fa" target="_blank" rel="noopener" aria-label="View page as Markdown">
        <i class="fa-regular fa-file-lines"></i> View page as Markdown <i class="fa-solid fa-arrow-up-right-from-square"></i>
    </a>
</div>
<h2 id="test-chunk">Test Chunking Strategy
    <a href="#test-chunk" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#test-chunk');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>Chunking quality depends on document structure and formatting. To improve chunking, test retrieval results by <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#retrieve-control">running retrieval queries</a> or, if the knowledge base is attached to an AI agent, by running <a href="/products/inference/how-to/evaluate-agents/">agent evaluations</a>.</p>
<p>To change chunking settings, <a href="/products/knowledge-bases/how-to/manage-data-sources/#remove-data-control">delete the data source</a>, and then <a href="/products/knowledge-bases/how-to/manage-data-sources/#add-data-control">add it again with the new chunking configuration</a>.</p>
<p>Since each indexing job consumes tokens, choose chunking settings carefully. For reference, semantic and hierarchical chunking can increase token usage, while section-based and fixed length chunking offer more predictable costs. For details on chunking costs, see <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">knowledge base pricing</a>.</p>
<h2 id="test-reranking">Test Reranking
    <a href="#test-reranking" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#test-reranking');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>Reranking can improve retrieval relevance by reordering results after the initial search so the most relevant chunks are more likely to appear first. To evaluate its impact, test retrieval results in the Control Panel, compare outputs with and without reranking enabled, and adjust the setting based on answer quality and cost.</p>
<p>To check and enable reranking, <a href="/products/knowledge-bases/how-to/edit-knowledge-bases/#edit-reranking">go to the knowledge base&rsquo;s <strong>Settings</strong> tab</a>.</p>
<p>Once reranking is enabled, reranking tokens are billed separately from vectorizing retrieval queries. For more information, see <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">knowledge base pricing</a>.</p>
<p>To test your reranking model, you can <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#retrieve-control">send queries to your knowledge base in the Control Panel</a>, <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#retrieve-api">use the DigitalOcean API</a>, or <a href="/products/knowledge-bases/how-to/test-knowledge-base-retrieval/">test retrieval and responses in RAG Playground</a>.</p>
<h2 id="retrieve-control">Retrieve Data from a Knowledge Base Using the Control Panel
    <a href="#retrieve-control" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#retrieve-control');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>Retrieve data from a knowledge base to test how well it returns relevant content for semantic, keyword, or hybrid searches. Results are returned as chunks, which are smaller sections of your source content along with any metadata attached during ingestion, such as category, product, source, or page information.</p>
<p>To retrieve data from a knowledge base, go to the <a href="https://cloud.digitalocean.com">Control Panel</a>, in the left menu, click <strong>DATA SERVICES</strong>, and then click the <strong>Knowledge Bases</strong> tab.</p>
<p>Then, click the knowledge base you want to query, and then click its <strong>Retrieve</strong> tab.</p>
<p>To enable reranking, <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#test-reranking">go to the knowledge base&rsquo;s <strong>Settings</strong> tab</a>. This means retrieved results are reordered by the reranking model to improve relevance.</p>
<p>If you want to disable reranking for one query, <a href="/products/knowledge-bases/how-to/edit-knowledge-bases/#edit-reranking">go to the knowledge base&rsquo;s <strong>Settings</strong> tab</a>, and click <strong>Disable reranking</strong>.</p>
<p>In the <strong>Search query</strong> field, type the text you want to search for.</p>
<p>In the <strong>num_results</strong> field, set how many results to return.</p>
<p>You can run one of the following search types against your knowledge base using the <strong>alpha</strong> field:</p>
<ul>
<li><strong>Semantic search</strong>: Finds results by meaning, even when the exact words do not match. Best for conversational or open-ended queries. Set <code>alpha: 1</code>.</li>
<li><strong>Keyword search</strong>: Finds results by exact word matches. Best for precise terms such as names, dates, IDs, or product codes. Set <code>alpha: 0</code>.</li>
<li><strong>Hybrid search</strong>: Combines semantic and keyword search in one result set. Best as the default for most queries. Start with <code>alpha: 0.5</code>, and then tune lower for more exact matching or higher for more meaning-based matching.</li>
</ul>
<p>An <strong>alpha</strong> value of <code>0</code> uses keyword retrieval, a value of <code>1</code> uses semantic retrieval, and values in between use hybrid retrieval.</p>
<p>Under the <strong>Filters (optional)</strong> tab, you can combine filters with <strong>and_all</strong>, which returns only chunks that match every condition, or <strong>or_all</strong>, which returns chunks that match at least one condition.</p>
<p>You can filter results by first clicking the <strong>Category</strong> dropdown list and choosing one of the following chunk metadata fields:</p>
<ul>
<li><strong>item_name</strong>: The source item name, such as a file name or URL path. For example, <code>https://docs.digitalocean.com/products/inference/</code>.</li>
<li><strong>ingested_timestamp</strong>: The date and time when the chunk was ingested into the knowledge base. For example, <code>2025-12-01T00:00:00Z</code>.</li>
<li><strong>page_number</strong>: The page number of the source document, when available. For example, <code>3</code>.</li>
<li><strong>chunk_category</strong>: The category assigned to the chunk during processing, such as the extracted content type.</li>
</ul>
<p>Then, click the condition dropdown to choose one of the following:</p>
<ul>
<li><strong>equals</strong>: Returns chunks where the field exactly matches the value. We recommend using this with <strong>item_name</strong> to target a specific file or URL, or with <strong>chunk_category</strong> when you want only one specific chunk type.</li>
<li><strong>not_equals</strong>: Excludes chunks where the field exactly matches the value.</li>
<li><strong>greater_than</strong>: Returns chunks where the field value is greater than the value you enter. We recommend using this with <strong>ingested_timestamp</strong> or <strong>page_number</strong> to filter by date or page range.</li>
<li><strong>greater_than_or_equals</strong>: Returns chunks where the field value is greater than or equal to the value you enter. We recommend using this with <strong>ingested_timestamp</strong> or <strong>page_number</strong> to filter by date or page range.</li>
<li><strong>less_than</strong>: Returns chunks where the field value is less than the value you enter. We recommend using this with <strong>ingested_timestamp</strong> or <strong>page_number</strong> to filter by date or page range.</li>
</ul>
<p>Then, in the <strong>Value</strong> field, enter the value for the filter.</p>
<p>To add a filter, click the <strong>+ Add condition</strong>. If you want to delete a filter, on the right of the filter condition, click <strong>x</strong>.</p>
<p>After setting up your search query, click <strong>Retrieve</strong>.</p>
<p>The <strong>Results</strong> section shows the total number of results retrieved, the query time in milliseconds (ms), the <strong>alpha</strong> value, and each retrieved chunk with its source file, page number when available, category metadata, and relevance score when available. Higher-relevance chunks are visually emphasized to help you spot the strongest matches more quickly.</p>
<p>If needed, you can also compare how different models answer questions using retrieved knowledge base content in the <a href="/products/knowledge-bases/how-to/test-knowledge-base-retrieval/">RAG Playground</a>.</p>
<h3 id="use-code-snippets-to-retrieve-data">Use Code Snippets to Retrieve Data
    <a href="#use-code-snippets-to-retrieve-data" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#use-code-snippets-to-retrieve-data');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Use the code snippets to turn your current retrieval settings into working API requests for testing, automation, or application development. This lets you reuse the same query, filters, and retrieval settings outside the Control Panel without writing the request from scratch.</p>
<p>To use the live auto-generated code snippets for the Gradient SDK (Python) or cURL based on your current query settings, click the <strong>Retrieve Endpoint</strong> tab, select the snippet you want from the code snippet dropdown list, and then click <strong>Copy</strong> to paste it where you need it or <strong>Download</strong> to save it.</p>
<h2 id="retrieve-api">Retrieve Data from a Knowledge Base Using the Knowledge Base API
    <a href="#retrieve-api" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#retrieve-api');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>You can query a knowledge base to retrieve the most relevant chunks, along with metadata, scores, and any hierarchical context. The knowledge base retrieve API is available at <code>https://kbaas.do-ai.run</code> and has the following endpoint:</p>
<div class="overflow-auto">
<table>
  <thead>
      <tr>
          <th style="text-align: left">Endpoint</th>
          <th style="text-align: left">Verb</th>
          <th style="text-align: left">Description</th>
      </tr>
  </thead>
  <tbody>
      <tr>
          <td style="text-align: left"><code>/v1/&lt;knowledge-base-uuid&gt;/retrieve</code></td>
          <td style="text-align: left">POST</td>
          <td style="text-align: left">Retrieves the most relevant chunks from a knowledge base using hybrid retrieval, combining keyword-based lexical retrieval with embedding-based semantic retrieval (and optional metadata filters).</td>
      </tr>
  </tbody>
</table>
</div>
<p>Data retrieval depends on how the knowledge base was configured and how the request is sent:</p>
<ul>
<li><strong>Chunking</strong> affects how content is split during indexing, which can affect retrieval results. Chunking is configured when you <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#test-chunk">create or update a knowledge base data source</a>, not during retrieval.</li>
<li><strong>Reranking</strong> optionally improves the ordering of retrieved results. If reranking is enabled for the knowledge base, you can disable it for an individual retrieval request.</li>
</ul>
<p>You can also call the retrieve endpoint using the <a href="https://gradient-sdk.digitalocean.com/api/python/resources/retrieve/methods/documents">Gradient SDK</a>.</p>
<p>To retrieve chunks from a knowledge base, send a POST request to <code>/v1/&lt;knowledge-base-uuid&gt;/retrieve</code> using your DigitalOcean API token. Requests to the retrieve API require a DigitalOcean API token created from the <a href="https://cloud.digitalocean.com/account/api/tokens"><strong>Settings</strong> page</a> with the <code>GenAI:read</code> scope enabled.</p>
<p>You can include the following fields in the request body:</p>
<ul>
<li>
<p><code>query</code>: Specifies the search query string.</p>
</li>
<li>
<p><code>num_results</code>: Defines the number between 0 and 100 of results to return.</p>
</li>
<li>
<p><code>alpha</code>: Controls the balance between lexical and semantic retrieval. Values range from <code>0</code> (lexical only) to <code>1</code> (semantic only). We recommend setting lower values for structured or technical queries, higher values for conversational or exploratory queries, and mid-range values for balanced precision and recall.</p>
</li>
<li>
<p><code>reranking</code>: Optionally controls reranking behavior for the request. Use this to disable reranking for an individual retrieval request.</p>
</li>
<li>
<p><code>filters</code>: Optionally narrows results by matching chunk metadata, such as:</p>
<ul>
<li><code>item_name</code>: The source item name, such as a file name or URL path.</li>
<li><code>ingested_timestamp</code>: The date and time when the chunk was ingested into the knowledge base.</li>
<li><code>page_number</code>: The page number of the source document, when available.</li>
<li><code>chunk_category</code>: The category assigned to the chunk during processing.</li>
</ul>
<p>Supported operations include:</p>
<ul>
<li><code>equals</code>: Matches values exactly. We recommend using this with <code>item_name</code> to target a specific file or URL, or with <code>chunk_category</code> to return one specific chunk type.</li>
<li><code>not_equals</code>: Excludes exact matches.</li>
<li><code>greater_than</code>: Matches values greater than the input. We recommend using this with <code>ingested_timestamp</code> or <code>page_number</code> to filter by date or page range.</li>
<li><code>greater_than_or_equals</code>: Matches values greater than or equal to the input. We recommend using this with <code>ingested_timestamp</code> or <code>page_number</code> to filter by date or page range.</li>
<li><code>less_than</code>: Matches values less than the input. We recommend using this with <code>ingested_timestamp</code> or <code>page_number</code> to filter by date or page range.</li>
<li><code>less_than_or_equals</code>: Matches values less than or equal to the input. We recommend using this with <code>ingested_timestamp</code> or <code>page_number</code> to filter by date or page range.</li>
<li><code>starts_with</code>: Matches text values that begin with the input. We recommend using this with <code>item_name</code> to restrict results to a specific file, URL, or path prefix.</li>
</ul>
<p>Combine filters with <code>and_all</code> to match all conditions or <code>or_all</code> to match any condition. You can also nest groups for more complex logic.</p>
</li>
</ul>
<p>The following example shows a hybrid retrieval request with no filters:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-bash" data-lang="bash"><span class="line"><span class="cl">curl --location <span class="s1">&#39;https://kbaas.do-ai.run/v1/&lt;knowledge-base-uuid&gt;/retrieve&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Content-Type: application/json&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Authorization: Bearer $DO_API_TOKEN&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--data <span class="s1">&#39;{
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;query&#34;: &#34;How do I build an agent on DigitalOcean?&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;num_results&#34;: 5,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;alpha&#34;: 0.5
</span></span></span><span class="line"><span class="cl"><span class="s1">}&#39;</span></span></span></code></pre></div>

<p>When using <code>filters</code>, the <code>key</code> must reference a metadata field in the dataset, and the <code>value</code> must match the field type, such as string, number, or boolean. Use operators compatible with the field type. For example, avoid <code>greater_than</code> on string fields unless they use a supported date or version format.</p>
<p>The following example uses <code>or_all</code> filter to return chunks where the source path starts with a specific documentation URL or the chunk was ingested on or after a specified date:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-bash" data-lang="bash"><span class="line"><span class="cl">curl --location <span class="s1">&#39;https://kbaas.do-ai.run/v1/&lt;knowledge-base-uuid&gt;/retrieve&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Content-Type: application/json&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Authorization: Bearer $DO_API_TOKEN&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--data <span class="s1">&#39;{
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;query&#34;: &#34;How do I build an agent on DigitalOcean&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;num_results&#34;: 5,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;filters&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;or_all&#34;: [
</span></span></span><span class="line"><span class="cl"><span class="s1">            {
</span></span></span><span class="line"><span class="cl"><span class="s1">                &#34;starts_with&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">                    &#34;key&#34;: &#34;item_name&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">                    &#34;value&#34;: &#34;https://docs.digitalocean.com/products/inference/&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">                },
</span></span></span><span class="line"><span class="cl"><span class="s1">                &#34;greater_than_or_equals&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">                    &#34;key&#34;: &#34;ingested_timestamp&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">                    &#34;value&#34;: &#34;2025-12-01&#34;
</span></span></span><span class="line"><span class="cl"><span class="s1">                }
</span></span></span><span class="line"><span class="cl"><span class="s1">            }
</span></span></span><span class="line"><span class="cl"><span class="s1">        ]
</span></span></span><span class="line"><span class="cl"><span class="s1">    },
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;alpha&#34;: 0.5
</span></span></span><span class="line"><span class="cl"><span class="s1">}&#39;</span></span></span></code></pre></div>

<p>The following example shows a response returned by the knowledge base API endpoint:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-json" data-lang="json"><span class="line"><span class="cl"><span class="p">{</span>
</span></span><span class="line"><span class="cl">    <span class="nt">&#34;results&#34;</span><span class="p">:</span> <span class="p">[</span>
</span></span><span class="line"><span class="cl">        <span class="p">{</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;metadata&#34;</span><span class="p">:</span> <span class="p">{</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;chunk_category&#34;</span><span class="p">:</span> <span class="s2">&#34;CompositeElement&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;ingested_timestamp&#34;</span><span class="p">:</span> <span class="s2">&#34;2025-12-15T15:23:19.191428+00:00&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;item_name&#34;</span><span class="p">:</span> <span class="s2">&#34;https://docs.digitalocean.com/products/inference/how-to/create-agents/&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">            <span class="p">},</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;text_content&#34;</span><span class="p">:</span> <span class="s2">&#34;Chunk 1 Content&#34;</span>
</span></span><span class="line"><span class="cl">        <span class="p">},</span>
</span></span><span class="line"><span class="cl">        <span class="p">{</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;metadata&#34;</span><span class="p">:</span> <span class="p">{</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;chunk_category&#34;</span><span class="p">:</span> <span class="s2">&#34;CompositeElement&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;ingested_timestamp&#34;</span><span class="p">:</span> <span class="s2">&#34;2025-12-15T15:23:19.191428+00:00&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;item_name&#34;</span><span class="p">:</span> <span class="s2">&#34;https://docs.digitalocean.com/products/inference/how-to/use-serverless-inference/&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">            <span class="p">},</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;text_content&#34;</span><span class="p">:</span> <span class="s2">&#34;Chunk2 content&#34;</span>
</span></span><span class="line"><span class="cl">        <span class="p">},</span>
</span></span><span class="line"><span class="cl">        <span class="err">...</span>
</span></span><span class="line"><span class="cl">    <span class="p">],</span>
</span></span><span class="line"><span class="cl">    <span class="nt">&#34;total_results&#34;</span><span class="p">:</span> <span class="mi">5</span>
</span></span><span class="line"><span class="cl"><span class="p">}</span></span></span></code></pre></div>

<p>Enable reranking for the request by setting the <code>enabled</code> parameter in <code>reranking</code> to <code>true</code> (or <code>false</code>).</p>
<p>The following example enables reranking for a hybrid retrieval request:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-bash" data-lang="bash"><span class="line"><span class="cl">curl --location <span class="s1">&#39;https://kbaas.do-ai.run/v1/&lt;knowledge-base-uuid&gt;/retrieve&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Content-Type: application/json&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--header <span class="s1">&#39;Authorization: Bearer $DO_API_TOKEN&#39;</span> <span class="se">\
</span></span></span><span class="line"><span class="cl">--data <span class="s1">&#39;{
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;query&#34;: &#34;How do I build an agent on DigitalOcean?&#34;,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;num_results&#34;: 5,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;alpha&#34;: 0.5,
</span></span></span><span class="line"><span class="cl"><span class="s1">    &#34;reranking&#34;: {
</span></span></span><span class="line"><span class="cl"><span class="s1">        &#34;enabled&#34;: true
</span></span></span><span class="line"><span class="cl"><span class="s1">    }
</span></span></span><span class="line"><span class="cl"><span class="s1">}&#39;</span></span></span></code></pre></div>

<p>The following example shows a reranked response returned by the knowledge base API endpoint:</p>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-json" data-lang="json"><span class="line"><span class="cl"><span class="p">{</span>
</span></span><span class="line"><span class="cl">    <span class="nt">&#34;results&#34;</span><span class="p">:</span> <span class="p">[</span>
</span></span><span class="line"><span class="cl">        <span class="p">{</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;metadata&#34;</span><span class="p">:</span> <span class="p">{</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;chunk_category&#34;</span><span class="p">:</span> <span class="s2">&#34;CompositeElement&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;ingested_timestamp&#34;</span><span class="p">:</span> <span class="s2">&#34;2025-12-15T15:23:19.191428+00:00&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;item_name&#34;</span><span class="p">:</span> <span class="s2">&#34;https://docs.digitalocean.com/products/inference/how-to/create-agents/&#34;</span>
</span></span><span class="line"><span class="cl">            <span class="p">},</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;text_content&#34;</span><span class="p">:</span> <span class="s2">&#34;Chunk 1 content&#34;</span>
</span></span><span class="line"><span class="cl">        <span class="p">},</span>
</span></span><span class="line"><span class="cl">        <span class="p">{</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;metadata&#34;</span><span class="p">:</span> <span class="p">{</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;chunk_category&#34;</span><span class="p">:</span> <span class="s2">&#34;CompositeElement&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;ingested_timestamp&#34;</span><span class="p">:</span> <span class="s2">&#34;2025-12-15T15:23:19.191428+00:00&#34;</span><span class="p">,</span>
</span></span><span class="line"><span class="cl">                <span class="nt">&#34;item_name&#34;</span><span class="p">:</span> <span class="s2">&#34;https://docs.digitalocean.com/products/inference/how-to/use-serverless-inference/&#34;</span>
</span></span><span class="line"><span class="cl">            <span class="p">},</span>
</span></span><span class="line"><span class="cl">            <span class="nt">&#34;text_content&#34;</span><span class="p">:</span> <span class="s2">&#34;Chunk 2 content&#34;</span>
</span></span><span class="line"><span class="cl">        <span class="p">}</span>
</span></span><span class="line"><span class="cl">    <span class="p">],</span>
</span></span><span class="line"><span class="cl">    <span class="nt">&#34;total_results&#34;</span><span class="p">:</span> <span class="mi">5</span>
</span></span><span class="line"><span class="cl">    <span class="err">...</span>
</span></span><span class="line"><span class="cl"><span class="p">}</span></span></span></code></pre></div>

</section>
        </main>

        <aside id="right-nav"><div id="right-menu">
                <p>In this article...</p><nav id="TableOfContents">
  <ul>
    <li><a href="#test-chunk">Test Chunking Strategy</a></li>
    <li><a href="#test-reranking">Test Reranking</a></li>
    <li><a href="#retrieve-control">Retrieve Data from a Knowledge Base Using the Control Panel</a>
      <ul>
        <li><a href="#use-code-snippets-to-retrieve-data">Use Code Snippets to Retrieve Data</a></li>
      </ul>
    </li>
    <li><a href="#retrieve-api">Retrieve Data from a Knowledge Base Using the Knowledge Base API</a></li>
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



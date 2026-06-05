Title: Live Content

Description: Fetched live

Source: https://docs.digitalocean.com/products/knowledge-bases/concepts/data-services-chunking-strategies/

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
<meta name="color-scheme" content="light dark"><meta name="description" content="Choose and configure chunking strategies to improve retrieval accuracy, reduce hallucinations, and optimize token usage when indexing knowledge bases.">

<meta name="generator" content="Hugo 0.161.1">

<meta name="google-site-verification" content="CAYPZwe7daX8KlYYZfB4VMjfT4g8Tqrrc4Q3g_wMvI8">

<meta name="og:site_name" content="DigitalOcean">
<meta name="og:type" content="article">

<meta name="twitter:site" content="DigitalOcean">
<meta name="twitter:creator" content="@DigitalOcean">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:url" content="https://docs.digitalocean.com/products/knowledge-bases/concepts/data-services-chunking-strategies/">

<link rel="canonical" href="https://docs.digitalocean.com/products/knowledge-bases/concepts/data-services-chunking-strategies/">
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
  "description": "Choose and configure chunking strategies to improve retrieval accuracy, reduce hallucinations, and optimize token usage when indexing knowledge bases.",
  "headline": "Chunking Best Practices for DigitalOcean Knowledge Base Indexing",
  "image": "https://www.digitalocean.com/_next/static/media/intro-to-cloud.d49bc5f7.jpeg",
  "inLanguage": "en",
  "keywords": "DigitalOcean, cloud computing",
  "mainEntityOfPage": {
    "@id": "https://docs.digitalocean.com/products/knowledge-bases/concepts/data-services-chunking-strategies/",
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
<title>Chunking Best Practices for DigitalOcean Knowledge Base Indexing | DigitalOcean Documentation</title>

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
    <li><a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/" class="primary active"><span class="menuText">Chunking Best Practices</span></a>

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
            href="/products/knowledge-bases/concepts/" itemid="/products/knowledge-bases/concepts/"
        >
            <span itemprop="name">Concepts</span>
        </a><meta itemprop="position" content="1" />
    </li><li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem"><span itemprop="name">Chunking Best Practices</span><meta itemprop="position" content="2" />
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
                    <h1>Chunking Best Practices for DigitalOcean Knowledge Base Indexing</h1><p>Validated on 15 Apr 2026 • Last edited on 8 May 2026</p>
<p id="product-summary">DigitalOcean Knowledge Bases let you store, index, and retrieve data from private files, websites, Spaces buckets, and other sources to power retrieval-augmented generation with your own content.</p></hgroup>

                <div class="md-tools">
    <a href="#" class="page-tool copy-text has-fa" data-copy-url="/products/knowledge-bases/concepts/data-services-chunking-strategies/index.html.md" aria-label="Copy page as Markdown">
        <i class="fa-regular fa-clipboard"></i> Copy page as Markdown
    </a>
    <a href="/products/knowledge-bases/concepts/data-services-chunking-strategies/index.html.md" class="page-tool view-markdown has-fa" target="_blank" rel="noopener" aria-label="View page as Markdown">
        <i class="fa-regular fa-file-lines"></i> View page as Markdown <i class="fa-solid fa-arrow-up-right-from-square"></i>
    </a>
</div>
<p>Chunking splits your documents into smaller, retrievable units before indexing. The chunking strategy you choose affects retrieval accuracy, indexing cost, and how much context your agent receives during inference. We support several chunking strategies, each configurable per data source.</p>
<p>This guide explains how to choose and tune chunking strategies. For parameter details, model-specific ranges, and recommendations, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/">chunking parameters reference</a> and the <a href="/products/knowledge-bases/details/knowledge-base-models/#embeddings-models">embeddings model catalog</a>. For cost details, see <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">knowledge base pricing</a>.</p>
<h2 id="general-best-practices">General Best Practices
    <a href="#general-best-practices" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#general-best-practices');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>We recommend the following:</p>
<ul>
<li>Start with the default chunking settings, which work well for most documents.</li>
<li>Configure chunking per data source and mix strategies within the same knowledge base.</li>
<li>Consider <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">indexing and storage costs</a> when choosing a strategy, as different chunking methods consume tokens differently.</li>
</ul>
<h2 id="choose-chunking-strategy">Choose Chunking Strategy
    <a href="#choose-chunking-strategy" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#choose-chunking-strategy');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>Chunking strategies can affect indexing and retrieval costs. Semantic chunking may increase indexing cost, while hierarchical chunking may increase retrieval cost because it returns parent and child chunks together. For parameter recommendations, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/">parameters reference</a>.</p>
<p>The sections below explain when to use each strategy and how each one behaves during indexing.</p>
<h3 id="section">Section-Based Chunking
    <a href="#section" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#section');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Uses structural elements such as headings, paragraphs, lists, tables, and callouts as natural boundaries. Adjacent sections are merged or split based on the maximum chunk size (<code>max_chunk_size</code>). Section-based chunking produces predictable, readable chunks.</p>
<p>Works best for:</p>
<ul>
<li>Product documentation</li>
<li>Policies and SOPs</li>
<li>FAQs</li>
<li>Blogs</li>
<li>Structured web content</li>
<li>Markdown files</li>
</ul>
<p>Choose this strategy if:</p>
<ul>
<li>Your document is already structured and has natural boundaries such as headings, paragraphs, lists, or tables.</li>
<li>You need predictable, readable chunks.</li>
<li>You want a fast, low-cost option.</li>
<li>You want a strong baseline for structured content.</li>
</ul>
<p>For more information, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/#section">section-based chunking reference</a> and the <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">pricing page</a>.</p>
<h3 id="semantic">Semantic Chunking
    <a href="#semantic" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#semantic');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Groups text by meaning using the chosen embeddings model. It performs two embedding passes:</p>
<ul>
<li>Detects semantic boundaries (<code>semantic_threshold</code>).</li>
<li>Embeds the final chunks (<code>max_chunk_size</code>).</li>
</ul>
<p>Semantic chunking produces more semantically aligned chunks, especially for documents without strong formatting.</p>
<p>Use when meaning matters more than formatting.</p>
<p>Works best for:</p>
<ul>
<li>Academic writing</li>
<li>Research notes</li>
<li>Long-form prose</li>
<li>Dense or inconsistently structured content</li>
</ul>
<p>Choose this strategy if:</p>
<ul>
<li>Your document groups content based on semantic similarity.</li>
<li>You need to detect topical shifts even when formatting is poor.</li>
<li>You need more accurate boundaries that reflect shifts in meaning.</li>
<li>You can accept higher indexing cost; semantic chunking may increase cost by 1.5 to 3 times compared to other strategies.</li>
</ul>
<p>For more information, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/#semantic">semantic chunking reference</a> and the <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">pricing page</a>.</p>
<h3 id="hierarchical">Hierarchical Chunking
    <a href="#hierarchical" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#hierarchical');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Creates a two-level structure consisting of:</p>
<ul>
<li>Parent chunks for broad context (<code>parent_chunk_size</code>).</li>
<li>Child chunks for precise retrieval (<code>child_chunk_size</code>).</li>
</ul>
<p>When a child chunk is retrieved, the system automatically includes its parent chunk to improve grounding.</p>
<p>Use when both broad context and precise retrieval are required.</p>
<p>Works best for:</p>
<ul>
<li>API reference documentation</li>
<li>Legal contracts</li>
<li>Product manuals</li>
<li>Highly structured technical content</li>
<li>Documents requiring long-context reasoning</li>
</ul>
<p>Choose this strategy if:</p>
<ul>
<li>You need both precise retrieval and broader contextual grounding.</li>
</ul>
<p>Hierarchical chunking has indexing costs similar to section-based strategies, but retrieval costs are higher because parent and child chunks are included together.</p>
<p>For more information, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/#hierarchical">hierarchical chunking reference</a> and the <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">pricing page</a>.</p>
<h3 id="fixed">Fixed Length Chunking
    <a href="#fixed" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#fixed');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h3>
<p>Splits text strictly by token count, ignoring formatting or meaning. This produces uniform chunk sizes and predictable indexing behavior.</p>
<p>Use when the document has unreliable formatting or when simplicity is preferred.</p>
<p>Works best for:</p>
<ul>
<li>Logs</li>
<li>IoT telemetry</li>
<li>OCR text</li>
<li>Time-series or streaming text</li>
<li>Machine-generated content</li>
<li>Code</li>
<li>Highly structured or repetitive data</li>
</ul>
<p>Choose this strategy if:</p>
<ul>
<li>You want chunking based solely on token count.</li>
<li>You can ignore document formatting and semantics.</li>
<li>You need a fast, predictable behavior.</li>
<li>You are indexing large-scale, unstructured, or repetitive content.</li>
</ul>
<p>For more information, see the <a href="/products/knowledge-bases/reference/data-services-chunking-strategies/#fixed">fixed length chunking reference</a> and the <a href="/products/knowledge-bases/details/pricing/#knowledge-bases">pricing page</a>.</p>
<h2 id="improve-chunking-performance">Improve Chunking Performance
    <a href="#improve-chunking-performance" class="anchor has-fa"
        onclick="navigator.clipboard.writeText(window.location.origin + window.location.pathname + '#improve-chunking-performance');"
    >
        <i class="fa-solid fa-link"></i>
    </a>
</h2>
<p>Chunking performance depends heavily on document clarity and formatting. To improve retrieval quality, follow these best practices:</p>
<ul>
<li>Start with the default chunking settings before tuning parameters.</li>
<li>Test retrieval using the <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#retrieve-control">knowledge base retrieval</a>.</li>
<li>Review retrieval quality using metrics such as context relevance, response-context completeness, context adherence, and retrieved chunk usage.</li>
<li>Adjust the <a href="/products/knowledge-bases/how-to/test-knowledge-bases/#test-chunk">chunking strategy or parameters</a> only when retrieval results show a clear issue.</li>
<li><a href="/products/knowledge-bases/how-to/index-data-sources/#re-index-control">Re-index the data source</a> after changing chunking settings.</li>
</ul>
<p>If you use the knowledge base with an <a href="/products/inference/">agent</a>, test it with <a href="/products/inference/how-to/evaluate-agents/">agent evaluations</a> to measure retrieval accuracy. For metric definitions, see the <a href="/products/inference/reference/agent-evaluation-metrics/">agent evaluation metrics reference page</a>.</p>
<p>Re-indexing consumes tokens, so make changes intentionally and avoid repeated small adjustments.</p>
</section>
        </main>

        <aside id="right-nav"><div id="right-menu">
                <p>In this article...</p><nav id="TableOfContents">
  <ul>
    <li><a href="#general-best-practices">General Best Practices</a></li>
    <li><a href="#choose-chunking-strategy">Choose Chunking Strategy</a>
      <ul>
        <li><a href="#section">Section-Based Chunking</a></li>
        <li><a href="#semantic">Semantic Chunking</a></li>
        <li><a href="#hierarchical">Hierarchical Chunking</a></li>
        <li><a href="#fixed">Fixed Length Chunking</a></li>
      </ul>
    </li>
    <li><a href="#improve-chunking-performance">Improve Chunking Performance</a></li>
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



<template>
  <section class="normal markdown-section">

    <h1 id="router-构造配置">Router 构造配置</h1>
    <h3 id="routes">routes</h3>
    <ul>
      <li>
        <p>类型:
          <code>Array&lt;RouteConfig&gt;</code>
        </p>
        <p>
          <code>RouteConfig</code> 的类型定义：</p>
        <pre><code class="lang-js">declare type RouteConfig = {
    path: string;
    component?: Component;
    name?: string; <span class="hljs-comment">// for named routes (命名路由)</span>
    components?: { [name: string]: Component }; <span class="hljs-comment">// for named views (命名视图组件)</span>
    redirect?: string | Location | <span class="hljs-built_in">Function</span>;
    alias?: string | <span class="hljs-built_in">Array</span>&lt;string&gt;;
    children?: <span class="hljs-built_in">Array</span>&lt;RouteConfig&gt;; <span class="hljs-comment">// for nested routes</span>
    beforeEnter?: (to: Route, <span class="hljs-keyword">from</span>: Route, next: <span class="hljs-built_in">Function</span>) =&gt; <span class="hljs-keyword">void</span>;
    meta?: any;
  }
  </code></pre>
      </li>
    </ul>
    <h3 id="mode">mode</h3>
    <ul>
      <li>
        <p>类型:
          <code>string</code>
        </p>
      </li>
      <li>
        <p>默认值:
          <code>"hash" (浏览器环境) | "abstract" (Node.js 环境)</code>
        </p>
      </li>
      <li>
        <p>可选值:
          <code>"hash" | "history" | "abstract"</code>
        </p>
        <p>配置路由模式:</p>
        <ul>
          <li>
            <p>
              <code>hash</code>: 使用 URL hash 值来作路由。支持所有浏览器，包括不支持 HTML5 History Api 的浏览器。</p>
          </li>
          <li>
            <p>
              <code>history</code>: 依赖 HTML5 History API 和服务器配置。查看
              <a href="../essentials/history-mode.html">HTML5 History 模式</a>.</p>
          </li>
          <li>
            <p>
              <code>abstract</code>: 支持所有 JavaScript 运行环境，如 Node.js 服务器端。
              <strong>如果发现没有浏览器的 API，路由会自动强制进入这个模式。</strong>
            </p>
          </li>
        </ul>
      </li>
    </ul>
    <h3 id="base">base</h3>
    <ul>
      <li>
        <p>类型:
          <code>string</code>
        </p>
      </li>
      <li>
        <p>默认值:
          <code>"/"</code>
        </p>
        <p>应用的基路径。例如，如果整个单页应用服务在
          <code>/app/</code> 下，然后
          <code>base</code> 就应该设为
          <code>"/app/"</code>。</p>
      </li>
    </ul>
    <h3 id="linkactiveclass">linkActiveClass</h3>
    <ul>
      <li>
        <p>类型:
          <code>string</code>
        </p>
      </li>
      <li>
        <p>默认值:
          <code>"router-link-active"</code>
        </p>
        <p>全局配置
          <code>&lt;router-link&gt;</code> 的默认『激活 class 类名』。参考
          <a href="router-link.html">router-link</a>.</p>
      </li>
    </ul>
    <h3 id="scrollbehavior">scrollBehavior</h3>
    <ul>
      <li>
        <p>类型:
          <code>Function</code>
        </p>
        <p>签名:</p>
        <pre><code>(
    to: Route,
    from: Route,
    savedPosition?: { x: number, y: number }
  ) =&gt; { x: number, y: number } | { selector: string } | ?{}
  </code></pre>
        <p>更多详情参考
          <a href="../advanced/scroll-behavior.html">滚动行为</a>.</p>
      </li>
    </ul>

  </section>
</template>

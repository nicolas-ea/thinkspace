<div class="container">

  <div class="projects-box mt-3">
    {% for post in site.posts %}
        {% if post.categories contains "projects" %}

          {% if post.categories contains "code" %}

          {% else %}

            {% if post.keywords contains "experimental" %}

            {% else %}
              <article class="post-item mt-3">
                <div class="article-title">

                  {% if post.link_post != nil  %}
                    {% assign proj_url = "#soon" %}
                    {% assign text_color_class = "style='color:#aaa;'" %}
                  {% else %}
                    {% assign proj_url = post.url | prepend: site.baseurl | prepend: site.url %}
                    {% assign text_color_class = "" %}
                  {% endif %}

                  <a class="post-link text-uppercase project-box project-{{ post.id_slug }}" href="{{ proj_url }}" hreflang="{% if post.language %}{{post.language}}{% else %}es{% endif %}" {{text_color_class}}>
                    {{ post.title }}
                  </a>
                  <span>{{ post.description }}</span>

                  <div class="container p-0 m-0">
                    {% for item in post.keywords %}
                      <span class="badge badge-light">{{ item }}</span>
                    {% endfor %}
                  </div>
                </div>

              </article>
            {% endif %}
          {% endif %}

        {% endif %}
    {% endfor %}
  </div>

  <br><hr><br>

  {% for post in site.posts %}
      {% if post.keywords contains "experimental" %}

      <article class="post-item mt-3">
        <div class="article-title">

          {% if post.link_post != nil  %}
            {% assign proj_url = "#soon" %}
            {% assign text_color_class = "style='color:#aaa;'" %}
          {% else %}
            {% assign proj_url = post.url | prepend: site.baseurl | prepend: site.url %}
            {% assign text_color_class = "" %}
          {% endif %}

          <a class="post-link text-uppercase project-box project-{{ post.id_slug }}" href="{{ proj_url }}" hreflang="{% if post.language %}{{post.language}}{% else %}es{% endif %}" {{text_color_class}}>
            {{ post.title }}
          </a>
          <span>{{ post.description }}</span>

          <div class="container p-0 m-0">
            {% for item in post.keywords %}
              <span class="badge badge-light">{{ item }}</span>
            {% endfor %}
          </div>
        </div>

      </article>

      {% endif %}
  {% endfor %}

  <br><hr><br>

  <div class="libs-box">
    <!-- <h2 class="over-title mt-4">Librerías</h2> -->

    {% for post in site.posts %}
        {% if post.categories contains "projects" %}

          {% if post.categories contains "code" %}

            <article class="post-item">
              <!-- <span class="post-meta date-label d-none d-lg-block">{{ post.date | date: "%m/%Y" }}</span> -->
              <div class="article-title">
                <a class="post-link" href="{{ post.url | prepend: site.baseurl | prepend: site.url }}" hreflang="{% if post.language %}{{post.language}}{% else %}es{% endif %}">

                  {% if post.categories contains "code" %}<span class="badge badge-light aaa">librería</span>{% endif %}
                  {{ post.title }}
                </a>

                <span>{{ post.description }}</span>
              </div>
            </article>
          {% endif %}

        {% endif %}
    {% endfor %}

  </div>

</div>

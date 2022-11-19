<ul 
id="mega-menu-primary"
class="mega-menu max-mega-menu mega-menu-horizontal"
data-event="hover"
data-effect="fade_up"
data-effect-speed="200"
data-effect-mobile="disabled"
data-effect-speed-mobile="0"
data-mobile-force-width="false"
data-second-click="close"
data-document-click="collapse"
data-vertical-behaviour="standard"
data-breakpoint="600"
data-unbind="true"
data-mobile-state="collapse_all"
data-hover-intent-timeout="300"
data-hover-intent-interval="100">

{% for link in site.data.navigation %}

{% assign current = nil %}
{% if page.url == link.url %}
    {% assign current = 'current' %}
{% endif %}
{% assign navIndex = {{forloop.index0}} %}

    {% if link.sections  %}
    <li class="mega-menu-item mega-menu-item-type-custom mega-menu-item-object-custom mega-menu-item-has-children mega-menu-megamenu mega-align-bottom-right mega-menu-grid mega-menu-item-{{navIndex}}" id="mega-menu-item-{{navIndex}}">
    <a class="mega-menu-link" href="{% if link.url=="" %} # {%else%} {{ link.url }} {% endif %}" aria-haspopup="true" aria-expanded="false" tabindex="0"> {{ link.text }} {% if link.indicator %} <span class="mega-indicator" data-has-click-event="true"></span> {% endif %}
    </a>

    {% else %}
    <li class="mega-menu-item mega-menu-item-type-post_type mega-menu-item-object-page mega-menu-megamenu mega-align-bottom-left mega-menu-megamenu mega-menu-item-{{navIndex}}" id="mega-menu-item-{{navIndex}}">
    <a class="mega-menu-link" href="{% if link.url=="" %} # {%else%} {{ link.url }} {% endif %}" tabindex="0" data-wpel-link="internal">{{link.text}}</a>
    
    {% endif%}


    <ul class="mega-sub-menu">
        <li class="mega-menu-row" id="mega-menu-{{navIndex}}-0">
        {% if link.sections  %}
        <ul class="mega-sub-menu">
            {% for sec in link.sections  %}
            {% assign secIndex = {{forloop.index0}} %}
            <li class="mega-menu-column mega-menu-columns-{{sec.column}}-of-2" id="mega-menu-{{navIndex}}-0-{{secIndex}}">
            <ul class="mega-sub-menu">
                <li class="mega-menu-item mega-menu-item-type-taxonomy mega-menu-item-object-category mega-menu-item-has-children mega-disable-link mega-menu-item-{{navIndex}}{{secIndex}}" id="mega-menu-item-{{navIndex}}{{secIndex}}">
                <a class="mega-menu-link" tabindex="0">{{sec.text}}<span class="mega-indicator" data-has-click-event="true"></span></a>
                
                {% if sec.category=="" and sec.menu %}
                <ul class="mega-sub-menu">
                    {% for item in sec.menu  %}
                    <li class="mega-menu-item mega-menu-item-type-custom mega-menu-item-object-custom mega-menu-item-{{navIndex}}{{secIndex}} {% if item.disable %} mega-disable-link {% endif %}" id="mega-menu-item-{{navIndex}}{{secIndex}}">
                    <a class="mega-menu-link" data-wpel-link="internal" href="{% if item.url=="" %} # {%else%} {{ item.url }} {% endif %}">{{item.text}}</a>
                    </li>
                    {% endfor %}
                </ul>

                {% else %}
                <ul class="mega-sub-menu">
                    {% for post in site.posts %}
                        {% unless post.categories contains sec.category %}{% continue %}{% endunless %}
                        <li class="mega-menu-item mega-menu-item-type-custom mega-menu-item-object-custom mega-menu-item-{{navIndex}}{{secIndex}} {% if post.location.ok != true %} mega-disable-link {% endif %}" id="mega-menu-item-{{navIndex}}{{secIndex}}">
                        <a class="mega-menu-link" data-wpel-link="internal" href="{{ post.url }}">{{post.title}}</a>
                        </li>        
                    {% endfor %}
                </ul>
                
                {% endif %}
                
                </li>
            </ul>
            </li>
            {% endfor %}
        </ul>
        {% endif %}
       </li>
    </ul>
    </li>

{% endfor %}

</ul>

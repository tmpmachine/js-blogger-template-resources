# Blog

## Default Markup
tags: #markup

```html
<!-- tags: # blog_widget -->
<b:defaultmarkup type='Blog'>
    <b:includable id='main'>

        <template class='WidgetData' expr:id='data:widget.instanceId'>
            <div>
                <!-- navigation -->
                <data key='newerPageUrl'>
                    <data:newerPageUrl />
                </data>
                <data key='olderPageUrl'>
                    <data:olderPageUrl />
                </data>

                <data key='posts[]'>
                    <b:with value='data:posts' var='posts'>
                        <b:loop values='data:posts' var='post'>
                            <div>
                                <data key='id'>
                                    <data:post.id />
                                </data>
                                <data key='url'>
                                    <data:post.url />
                                </data>
                                <data key='title'>
                                    <data:post.title />
                                </data>
                                <data key='date'>
                                    <data:post.date />
                                </data>
                                <data type='node' key='body'>
                                    <data:post.body />
                                </data>
                                <data key='appRpcRelayPath'>
                                    <data:post.appRpcRelayPath />
                                </data>
                                <data key='commentFormIframeSrc'>
                                    <data:post.commentFormIframeSrc />
                                </data>
                                <data key='cmtfpIframe'>
                                    <data:post.cmtfpIframe />
                                </data>
                                <data key='commentsUrl'>
                                    <data:post.commentsUrl />
                                </data>
                                <data key='commentsUrlOnclick'>
                                    <data:post.commentsUrlOnclick />
                                </data>

                                <data key='labels[]'>
                                    <b:loop values='data:post.labels' var='label'>
                                        <div>
                                            <data key='url'>
                                                <data:label.url />
                                            </data>
                                            <data key='name'>
                                                <data:laabel.name />
                                            </data>
                                        </div>
                                    </b:loop>
                                </data>
                            </div>
                        </b:loop>
                    </b:with>
                </data>

            </div>
        </template>

        <!-- post metadata -->
        <b:loop values='data:posts' var='post'>
            <b:if cond='data:view.isSingleItem'>
                <b:include data='post' name='postMetadataJSON' />
            </b:if>
        </b:loop>

    </b:includable>
</b:defaultmarkup>
```

## Usage Example
tags: #example

```html
<template id="Blog">
    <div b-data="posts" b-template="PostWidget"></div>

    <!-- tags: #pagination, #nav -->
    <a b-attr-href="olderPageUrl">Older Post</a>
</template>

<template id="PostWidget">
    <!-- title -->
    <h2><a b-attr-href="url" b-data="title"></a></h2>
    <!-- date -->
    <span b-data="date"></span>
    <!-- body -->
    <div b-data="body"></div>
</template>
```
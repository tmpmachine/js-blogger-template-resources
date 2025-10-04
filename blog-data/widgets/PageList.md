# PageList

## Default Markup

```html
<!-- # pagelist -->
<b:defaultmarkup type='PageList'>
  <b:includable id='main'>
    <template class='WidgetData' expr:id='data:widget.instanceId'>
      <div>
        <data key='title'>
          <data:title />
        </data>
        <data key='links[]'>
          <b:loop values='data:links' var='link'>
            <div>
              <data key='href'>
                <data:link.href />
              </data>
              <data key='title'>
                <data:link.title />
              </data>
              <data key='isCurrentPage' type='boolean'>
                <data:link.isCurrentPage />
              </data>
            </div>
          </b:loop>
        </data>
      </div>
    </template>
  </b:includable>
</b:defaultmarkup>
```
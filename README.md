# vue-components
A Vue@Next Component Library  
This library is primarily for use by web applications written using the Vue@Next framework.
It contains common, reusable components agnostic to the Application that incorporates it.
All data and functionality are either passed through Props, Imported or Provided by the parent.

There should be no outside dependencies on any libraries or code ie: jQuery, Vue Plugins or Extensions, fetch.
Any request for external services will be passed by Props or Provided. Imports must files local to the vue-components library.

Nomenclature:
  Event Handlers: on&lt;-action-name&gt; turning into on&lt;ActionName&gt;
  Prop Handlers: fn&lt;-action-name&gt; turning into fn&lt;ActionName&gt;
  
Local Dynamic Styling Support:
  
#This Login template example expects the Login component has a members

- formDisplay which returns a valid display style ie:grid, flex, none, etc
- Email:{name:"emailaddress",placeholder:"Enter your email"}
- Password:{}
- Submit:{is:"button",type:"submit"}

<pre>
&lt;div&gt;
&lt;component is="style"&gt;
form.login-form{
  display:{{formDisplay || 'grid'}}
}
&lt;/component&gt;
  &lt;form class="login-form" &gt;
  &lt;input :name="Email.name||'email'" :type="Email.type || 'email'" :placeholder="Email.placeholder || 'Enter your email address'" /&gt;
  &lt;input :name="Password.name||'password'" :type="Password.type || 'password'" :placeholder="Password.placeholder || 'Password'" /&gt;
  &lt;component :is="Submit.is" :type="Submit.type" &gt;{{Submit.text || 'Login'}}&lt;/component&gt;
  &lt;/form&gt;
&lt;/div&gt;
</pre>

---


---

<p>#Fragment</p>
<p><strong>EXPERIMENT 5- To incorporate element of interactivity using Android Fragment and Intent Class.</strong></p>
<p>&lt;![endif]–&gt;</p>
<p>A <strong>Fragment</strong> is a piece of an activity which enable more modular activity design. It will not be wrong if we say, a fragment is a kind of <strong>sub-activity</strong>.</p>
<p>Following are important points about fragment −</p>
<p>A fragment has its own layout and its own behaviour with its own life cycle callbacks.<br>
You can add or remove fragments in an activity while the activity is running.</p>
<p>You can combine multiple fragments in a single activity to build a multi-pane UI.</p>
<p>A fragment can be used in multiple activities.</p>
<p>Fragment life cycle is closely related to the life cycle of its host activity which means when the activity is paused, all the fragments available in the activity will also be stopped.</p>
<p>A fragment can implement a behaviour that has no user interface component.</p>
<p>Fragments were added to the Android API in Honeycomb version of Android which API version 11.</p>
<p>You create fragments by extending <strong>Fragment</strong> class and You can insert a fragment into your activity layout by declaring the fragment in the activity’s layout file, as a <strong></strong> element.</p>
<p>Prior to fragment introduction, we had a limitation because we can show only a single activity on the screen at one given point in time. So we were not able to divide device screen and control different parts separately. But with the introduction of fragment we got more flexibility and removed the limitation of having a single activity on the screen at a time. Now we can have a single activity but each activity can comprise of multiple fragments which will have their own layout, events and complete life cycle.</p>
<p>Following is a typical example of how two UI modules defined by fragments can be combined into one activity for a tablet design, but separated for a handset design.</p>
<p>The application can embed two fragments in Activity A, when running on a tablet-sized device. However, on a handset-sized screen, there’s not enough room for both fragments, so Activity A includes only the fragment for the list of articles, and when the user selects an article, it starts Activity B, which includes the second fragment to read the article.<img src="https://github.com/shubham120497/5.-To-incorporate-element-of-interactivity-using-Android-Fragment-and-Intent-Class/blob/master/android_fragments.jpg" alt="enter image description here"></p>
<p>&lt;![endif]–&gt;</p>
<p>Fragment Life Cycle</p>
<p>Android fragments have their own life cycle very similar to an android activity. This section briefs different stages of its life cycle.</p>
<p>Here is the list of methods which you can to override in your fragment class −</p>
<p>**onAttach()**The fragment instance is associated with an activity instance.The fragment and the activity is not fully initialized. Typically you get in this method a reference to the activity which uses the fragment for further initialization work.</p>
<p><strong>onCreate()</strong> The system calls this method when creating the fragment. You should initialize essential components of the fragment that you want to retain when the fragment is paused or stopped, then resumed.</p>
<p><strong>onCreateView()</strong> The system calls this callback when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a <strong>View</strong> component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.</p>
<p>**onActivityCreated()**The onActivityCreated() is called after the onCreateView() method when the host activity is created. Activity and fragment instance have been created as well as the view hierarchy of the activity. At this point, view can be accessed with the findViewById() method. example. In this method you can instantiate objects which require a Context object</p>
<p>**onStart()**The onStart() method is called once the fragment gets visible.</p>
<p>**onResume()**Fragment becomes active.</p>
<p><strong>onPause()</strong> The system calls this method as the first indication that the user is leaving the fragment. This is usually where you should commit any changes that should be persisted beyond the current user session.</p>
<p>**onStop()**Fragment going to be stopped by calling onStop()</p>
<p>**onDestroyView()**Fragment view will destroy after call this method</p>
<p>**onDestroy()**onDestroy() called to do final clean up of the fragment’s state but Not guaranteed to be called by the Android platform</p>
<p>#INTENT<br>
&lt;![endif]–&gt;</p>
<h1 id="android-intent"><strong>Android Intent</strong></h1>
<p>&lt;![if !vml]&gt;![android intent](file:///C:/Users/SHUBHA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)&lt;![endif]&gt;</p>
<p><strong>Android Intent</strong> is the <em>message</em> that is passed between components such as activities, content providers, broadcast receivers, services etc.</p>
<p>It is generally used with startActivity() method to invoke activity, broadcast receivers etc.</p>
<p>The <strong>dictionary meaning</strong> of intent is <em>intention or purpose</em>. So, it can be described as the intention to do action.</p>
<p>The LabeledIntent is the subclass of android.content.Intent class.</p>
<p>Android intents are mainly used to:</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Start the service</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Launch an activity</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Display a web page</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Display a list of contacts</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Broadcast a message</p>
<p>&lt;![if !supportLists]&gt;o &lt;![endif]&gt;Dial a phone call etc.</p>
<h2 id="types-of-android-intents">Types of Android Intents</h2>
<p>There are two types of intents in android: implicit and explicit.</p>
<h3 id="implicit-intent"><strong>1) Implicit Intent</strong></h3>
<p><strong>Implicit Intent</strong> doesn’t specifiy the component. In such case, intent provides information of available components provided by the system that is to be invoked.</p>
<p>For example, you may write the following code to view the webpage.</p>
<p>Intent intent=<strong>new</strong> Intent(Intent.ACTION_VIEW);<br>
intent.setData(Uri.parse(“<a href="http://www.javatpoint.com">http://www.javatpoint.com</a>”));</p>
<p>startActivity(intent);</p>
<h3 id="explicit-intent"><strong>2) Explicit Intent</strong></h3>
<p><strong>Explicit Intent</strong> specifies the component. In such case, intent provides the external class to be invoked.</p>
<p>Intent i = <strong>new</strong> Intent(getApplicationContext(), ActivityTwo.<strong>class</strong>);<br>
<strong>strong text</strong><br>
startActivity(i);</p>


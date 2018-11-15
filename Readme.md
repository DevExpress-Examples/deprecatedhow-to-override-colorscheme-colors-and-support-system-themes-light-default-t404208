<!-- default file list -->
*Files to look at*:

* [App.xaml](./CS/App.xaml) (VB: [App.xaml](./VB/App.xaml))
* **[OverrideColors.xaml](./CS/Themes/OverrideColors.xaml) (VB: [OverrideColors.xaml](./VB/Themes/OverrideColors.xaml))**
<!-- default file list end -->
# [Deprecated]How to override ColorScheme colors and support system themes (Light|Default)


Starting with <strong>v17.1</strong>, we provide a more powerful and flexible way of overriding predefined colors. Refer to the updated <a href="https://www.devexpress.com/Support/Center/p/T505750">How to override default colors from an existing Color Scheme in Windows 10 XAML controls and support system themes (Light, Default) </a> example for more information.<br>
<p><br>This example illustrates how to override default colors from an existing color scheme in Windows 10 XAML controls and support system themes (Light, Default). In the current implementation, the background of the <strong>RibbonControl</strong> header is overridden in <strong>Generic</strong> and <strong>Win8</strong> schemes and has different values in these schemes for the <strong><em>Default</em></strong> and <strong><em>Light</em></strong> system themes.</p>
<p>Colors should be overridden within a separate ResourceDictionary file and used in the <strong>Source </strong>property of the <strong>GlobalColorSchemeOverrider</strong> class.<br><br>Certain system theme colors must be declared in a separate ResourceDictionary in the color scheme ResourceDictionary's ThemeDictionary collection as follows: </p>
<p> </p>


```xaml
    <ResourceDictionary x:Key="Generic">
        <ResourceDictionary.ThemeDictionaries>
            <ResourceDictionary x:Key="Default">
                <SolidColorBrush x:Key="RibbonHeaderBackgroundBrush" Color="#FF164B2F"/>
                ...
            </ResourceDictionary>
            <ResourceDictionary x:Key="Light">
                <SolidColorBrush x:Key="RibbonHeaderBackgroundBrush" Color="#FF418366"/>
                ...
            </ResourceDictionary>
        </ResourceDictionary.ThemeDictionaries>

        ...  
    </ResourceDictionary>

```


<p><strong> </strong> </p>
<p><strong>Note: </strong><br>1. Our controls have the same appearance in different system themes when the <strong>Win8</strong> color scheme is applied. System themes are supported in our controls out of the box only when the <strong>Generic</strong> color scheme is applied. <br>2. The <strong><em>Dark </em></strong>system theme is determined as <strong><em>Default </em></strong>and colors in the <strong>Generic </strong>color scheme for both these themes are the same.</p>
<p><strong> <br></strong>All colors available for overriding are listed in separate files within the installation folder with our controls: <DevExpress Installation Folder><strong><u>\Components\System\UAP\ColorThemes</u></strong></p>

<br/>



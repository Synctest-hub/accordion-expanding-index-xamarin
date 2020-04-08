# How to retrieve the expanding Accordion item index in Xamarin.Forms (SfAccordion)?

You can get the index of [AccordionItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.AccordionItem.html?) when expanding in Xamarin.Forms [SfAccordion](https://help.syncfusion.com/xamarin/accordion/getting-started?).

You can also refer the following article.

https://www.syncfusion.com/kb/11358/how-to-retrieve-the-expanding-accordion-item-index-in-xamarin-forms-sfaccordion

**C#**

You can get the index from the [ExpandingAndCollapsingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.ExpandingAndCollapsingEventArgs.html?) of the [Expanding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.SfAccordion~Expanding_EV.html?) event.

``` c#
namespace AccordionXamarin.Behavior
{
    public class Behavior : Behavior<SfAccordion>
    {
        SfAccordion Accordion;
 
        protected override void OnAttachedTo(SfAccordion bindable)
        {
            Accordion = bindable;
            Accordion.Expanding += Accordion_Expanding;
            base.OnAttachedTo(bindable);
        }
 
        private void Accordion_Expanding(object sender, ExpandingAndCollapsingEventArgs e)
        {
            App.Current.MainPage.DisplayAlert("", "AccordionItem expanded at index " + e.Index, "Ok");
        }
    }
}
```

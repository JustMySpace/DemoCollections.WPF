SourceURL https://kmatyaszek.github.io/wpf%20validation/2019/03/13/wpf-validation-using-inotifydataerrorinfo.html

Code Copy From https://github.com/kmatyaszek/WPFValidationINotifyDataErrorInfo
Removed dependent of Prism

In the .NET 4.5 was introduced new interface INotifyDataErrorInfo which enables data entity classes to implement custom validation rules and expose validation results asynchronously. This interface has three members:

* HasErrors property indicates whether there are any validation errors
* GetErrors method returns an IEnumerable that contains validation errors for the specified property (when the propertyName parameter isn’t equal to null or empty string) or for the entire entity (when the propertyName parameter is equal to null or empty string)
* ErrorsChanged event must occur when the validation errors have changed for a property or for the entity

As GetErrors returns IEnumerable you can return multiple errors per property. Also, you can return custom error object (this is not possible using IDataErrorInfo interface). As you can see this new interface provides more flexible validation model in WPF. By default, ValidatesOnNotifyDataErrors is set to true so you don’t have to set this explicit in the binding expression. Below you can see the result of my example program (as you can see TextBox has two errors).

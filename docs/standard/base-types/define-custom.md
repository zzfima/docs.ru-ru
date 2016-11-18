---
title: "Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов"
description: "Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9b184114-6612-4c1a-a2db-2e24e65b0f77
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: bb62bdd03d4af4f764ac3bc8734c67902fffa798

---

# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов

.NET обеспечивает расширенный контроль над строковым представлением числовых значений. Эта платформа поддерживает указанные далее возможности для настройки форматов числовых значений.

* Строки стандартных числовых форматов, которые предоставляют стандартный набор форматов для преобразования чисел в их строковое представление. Их можно использовать с любым методом числового форматирования, например [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)) с параметром format. Дополнительные сведения см. в разделе [Строки стандартных числовых форматов](standard-numeric.md).

* Строки настраиваемых числовых форматов, предоставляющих набор символов, которые могут быть объединены для определения описателей настраиваемого числового формата. Их также можно использовать с любым методом числового форматирования, например [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)) с параметром format. Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](custom-numeric.md).

* Настраиваемые объекты [CultureInfo](xref:System.Globalization.CultureInfo) или [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), которые определяют символы и шаблоны форматирования, используемые при отображении строковых представлений числовых значений. Их можно использовать с любым методом числового форматирования, например [ToString](xref:System.Int32.ToString(System.IFormatProvider)) с параметром *provider*. Как правило, параметр *provider* используется для указания форматирования, зависящего от языка и региональных параметров.

В некоторых случаях (например, когда приложению необходимо отобразить отформатированный номер учетной записи, идентификационный номер или почтовый индекс) эти три метода неприменимы. .NET также позволяет определить объект форматирования, который не является ни [CultureInfo](xref:System.Globalization.CultureInfo), ни объектом [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), для определения порядка форматирования числовых значений. Этот раздел содержит пошаговые инструкции по реализации таких объектов и пример форматирования телефонных номеров.

## <a name="to-define-a-custom-format-provider"></a>Определение поставщика пользовательского формата

1. Определите класс, который реализует интерфейсы [IFormatProvider](xref:System.IFormatProvider) и [ICustomFormatter](xref:System.ICustomFormatter). 

2. Реализуйте метод [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). Метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) представляет собой метод обратного вызова, который вызывается методом форматирования (таким как метод [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))) для получения объекта, фактически отвечающего за выполнение пользовательского форматирования. Обычная реализация метода [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) выполняет следующие действия.

    1. Определяет, представляет ли объект [Type](xref:System.Type), передаваемый в качестве параметра метода, интерфейс [ICustomFormatter](xref:System.ICustomFormatter).
    
    2. Если параметр представляет собой интерфейс [ICustomFormatter](xref:System.ICustomFormatter), то метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) возвращает объект, реализующий интерфейс [ICustomFormatter](xref:System.ICustomFormatter), который отвечает за предоставление пользовательского форматирования. Как правило, объект пользовательского форматирования возвращает сам себя. 
    
    В. Если параметр не представляет собой интерфейс [ICustomFormatter](xref:System.ICustomFormatter), то метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) возвращает `null`.
    
3. Реализуйте метод [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)). Этот метод вызывается методом [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) и возвращает строковое представление числа. Реализация этого метода обычно включает в себя выполнение следующих действий.

    1. При необходимости убедитесь, что метод предназначен для предоставления служб форматирования, проверив параметр *provider*. Для объектов форматирования, реализующих интерфейс [IFormatProvider](xref:System.IFormatProvider) и [ICustomFormatter](xref:System.ICustomFormatter), это включает в себя проверку параметра *provider* на равенство с текущим объектом форматирования.
    
    2. Определите, должен ли объект форматирования поддерживать описатели настраиваемого формата. (Например, описатель формата "N" может указывать, что телефонный номер США следует выводить в формате NANP, а "I" может означать вывод в формате E.123 в соответствии с рекомендацией ITU-T.) Если используются описатели формата, то метод должен обрабатывать этот описатель определенного формата. Он передается методу в параметре format. Если описатель отсутствует, значением параметра *format* является [String.Empty](xref:System.String#System_String_Empty).
    
    В. Получите числовое значение, передаваемое в метод в качестве параметра *arg*. Выполните операции, необходимые для его преобразования в строковое представление.
    
    d. Возвращает строковое представление параметра *arg*.
    
## <a name="to-use-a-custom-numeric-formatting-object"></a>Использование объекта настраиваемого числового форматирования

1. Создайте новый экземпляр класса настраиваемого форматирования.

2. Вызовите метод форматирования [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), передавая ему объект настраиваемого форматирования, описатель форматирования (или [String.Empty](xref:System.String.Empty), если он не используется) и числовое значение для форматирования. 

## <a name="example"></a>Пример

В следующем примере определяется поставщик настраиваемого числового формата с именем `TelephoneFormatter`, который преобразует число, представляющее номер телефона в США, в формат NANP или E.123. Метод обрабатывает два описателя формата "N" (вывод в формате NANP) и "I" (вывод в международном формате E.123).

```csharp
using System;
using System.Globalization;

public class TelephoneFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   {
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }               

   public string Format(string format, object arg, IFormatProvider formatProvider)
   {
      // Check whether this is an appropriate callback             
      if (! this.Equals(formatProvider))
         return null; 

      // Set default format specifier             
      if (string.IsNullOrEmpty(format)) 
         format = "N";

      string numericString = arg.ToString();

      if (format == "N")
      {
         if (numericString.Length <= 4)
            return numericString;
         else if (numericString.Length == 7)
            return numericString.Substring(0, 3) + "-" + numericString.Substring(3, 4); 
         else if (numericString.Length == 10)
               return "(" + numericString.Substring(0, 3) + ") " +
                      numericString.Substring(3, 3) + "-" + numericString.Substring(6);   
         else
            throw new FormatException( 
                      string.Format("'{0}' cannot be used to format {1}.", 
                                    format, arg.ToString()));
      }
      else if (format == "I")
      {
         if (numericString.Length < 10)
            throw new FormatException(string.Format("{0} does not have 10 digits.", arg.ToString()));
         else
            numericString = "+1 " + numericString.Substring(0, 3) + " " + numericString.Substring(3, 3) + " " + numericString.Substring(6);
      }
      else
      {
         throw new FormatException(string.Format("The {0} format specifier is invalid.", format));
      } 
      return numericString;  
   }
}

public class TestTelephoneFormatter
{
   public static void Main()
   {
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:I}", 4257884748));
   }
}
```

```vb
Public Class TelephoneFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If               
   End Function               

   Public Function Format(fmt As String, arg As Object, _
                          formatProvider As IFormatProvider) As String _
                   Implements ICustomFormatter.Format
      ' Check whether this is an appropriate callback             
      If Not Me.Equals(formatProvider) Then Return Nothing 

      ' Set default format specifier             
      If String.IsNullOrEmpty(fmt) Then fmt = "N"

      Dim numericString As String = arg.ToString

      If fmt = "N" Then
         Select Case numericString.Length
            Case <= 4 
               Return numericString
            Case 7
               Return Left(numericString, 3) & "-" & Mid(numericString, 4) 
            Case 10
               Return "(" & Left(numericString, 3) & ") " & _
                      Mid(numericString, 4, 3) & "-" & Mid(numericString, 7)   
            Case Else
               Throw New FormatException( _
                         String.Format("'{0}' cannot be used to format {1}.", _
                                       fmt, arg.ToString()))
         End Select
      ElseIf fmt = "I" Then
         If numericString.Length < 10 Then
            Throw New FormatException(String.Format("{0} does not have 10 digits.", arg.ToString()))
         Else
            numericString = "+1 " & Left(numericString, 3) & " " & Mid(numericString, 4, 3) & " " & Mid(numericString, 7)
         End If      
      Else
         Throw New FormatException(String.Format("The {0} format specifier is invalid.", fmt))
      End If 
      Return numericString  
   End Function
End Class

Public Module TestTelephoneFormatter
   Public Sub Main
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:I}", 4257884748))
   End Sub
End Module
```

Поставщик настраиваемого числового формата может использоваться только с методом [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Другие перегрузки методов числового форматирования (например, `ToString`) с параметром типа [IFormatProvider](xref:System.IFormatProvider) передают реализацию метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) для объекта [Type](xref:System.Type), представляющего тип [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). В свою очередь, они ожидают, что метод вернет объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). Если это не так, поставщик настраиваемого числового формата игнорируется, и вместо него используется объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), соответствующий текущим языку и региональным параметрам. В примере метод `TelephoneFormatter.GetFormat` обрабатывает вероятность некорректной передачи методу числового форматирования, проверяя параметр метода и возвращая *null*, если он представляет тип, отличный от [ICustomFormatter](xref:System.ICustomFormatter).

Если поставщик настраиваемого числового формата поддерживает набор описателей формата, убедитесь, что также предоставлено поведение по умолчанию, если описатель формата не предоставляется в элементе форматирования, используемом при вызове метода [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). В приведенном примере "N" является описателем формата по умолчанию. Это позволяет преобразовать число в формат телефонного номера, явно предоставляя описатель формата. В следующем примере показан такой вызов метода.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))
```

Но это также позволяет выполнить преобразование в случае, если описатель формата отсутствует. В следующем примере показан такой вызов метода.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))
```

Если описатель формата по умолчанию не определен, реализация метода [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) должна содержать код, аналогичный приведенному ниже, чтобы в .NET могло быть представлено форматирование, которое не поддерживается кодом.

```csharp
if (arg is IFormattable) 
   s = ((IFormattable)arg).ToString(format, formatProvider);
else if (arg != null)    
   s = arg.ToString();
```

```vb
If TypeOf(arg) Is IFormattable Then 
   s = DirectCast(arg, IFormattable).ToString(fmt, formatProvider)
ElseIf arg IsNot Nothing Then    
   s = arg.ToString()
End If
```

В таком случае в этом примере метод, реализующий [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), служит методом обратного вызова для метода [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Таким образом, он проверяет параметр *formatProvider* на наличие ссылки на текущий объект `TelephoneFormatter`. Тем не менее, метод можно также вызвать непосредственно из кода. В этом случае можно использовать параметр *formatProvider* для предоставления [CultureInfo](xref:System.Globalization.CultureInfo) или объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющего сведения о форматировании для соответствующих языка и региональных параметров.

## <a name="see-also"></a>См. также

[Выполнение операций форматирования](performing-formatting-operations.md)



<!--HONumber=Nov16_HO3-->



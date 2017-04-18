---
title: "Сведения о вызывающем (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a4b63fb424ad6aef9d1bd56f43ccccd79f0b9b3
ms.lasthandoff: 03/13/2017

---
# <a name="caller-information-visual-basic"></a>Сведения о вызывающем (Visual Basic)
С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода. Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта. Эти сведения полезны для трассировки, отладки и создания средств диагностики.  
  
 Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию. В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в <xref:System.Runtime.CompilerServices?displayProperty=fullName>пространство имен:</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|Атрибут|Описание|Тип|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Полный путь исходного файла, содержащего вызывающий объект. Это путь к файлу во время компиляции.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Номер строки в исходном файле, в которой вызывается метод.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Имя свойства или метода вызывающего объекта. В разделе [имена членов](#MEMBERNAMES) далее в этом разделе.|`String`|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать информационные атрибуты вызывающего объекта. При каждом вызове метода `TraceMessage` сведения о вызывающем объекте подставляются в качестве аргументов необязательных параметров.  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a>Заметки  
 Для каждого необязательного параметра необходимо указать явное значение по умолчанию. Нельзя применять информационные атрибуты вызывающего объекта к параметрам, которые не были указаны как необязательные.  
  
 Информационные атрибуты вызывающего объекта не делают параметр необязательным. Вместо этого они влияют на значение по умолчанию, которое передается, если аргумент был опущен.  
  
 Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции. В отличие от результатов <xref:System.Exception.StackTrace%2A>свойство для исключений, результаты не затрагиваются запутывания.</xref:System.Exception.StackTrace%2A>  
  
 Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.  
  
###  <a name="MEMBERNAMES"></a>Имена членов  
 Можно использовать атрибут `CallerMemberName`, чтобы не указывать имя члена в виде аргумента `String` вызываемому методу. С помощью этого метода позволяет избежать проблемы, **рефакторинга и переименования** не изменяет `String` значения. Это особенно полезно при выполнении следующих задач:  
  
-   Использование процедур трассировки и диагностики.  
  
-   Реализация <xref:System.ComponentModel.INotifyPropertyChanged>интерфейса при привязке данных.</xref:System.ComponentModel.INotifyPropertyChanged> Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения. Если атрибут `CallerMemberName` не используется, необходимо указать имя свойства как литерал.  
  
 В следующей таблице представлены имена членов, возвращаемых при использовании атрибута `CallerMemberName`.  
  
|Фрагмент кода, в пределах которого происходит вызов|Результат имени члена|  
|-------------------------|------------------------|  
|Метод, свойство или событие|Имя метода, свойства или события, из которого происходил вызов.|  
|Конструктор|Строка ".ctor"|  
|Статический конструктор|Строка ".cctor"|  
|Деструктор|Строка "Finalize"|  
|Определяемые пользователем операторы и преобразования|Созданное имя члена, например, "op_Addition".|  
|Конструктора атрибута|Имя члена, к которому применяется атрибут. Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.|  
|Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)|Значение необязательного параметра по умолчанию.|  
  
## <a name="see-also"></a>См. также  
 [Атрибуты (Visual Basic)](../../../visual-basic/language-reference/attributes.md)   
 [Общие атрибуты (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)   
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Основные понятия программирования (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)

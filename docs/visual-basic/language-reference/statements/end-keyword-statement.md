---
title: Конец &lt;ключевое слово&gt; Statement (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 7fe772c6c05a982153655d618c826e9839d39cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2018
ms.locfileid: "33605268"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>Конец &lt;ключевое слово&gt; Statement (Visual Basic)

Когда следует дополнительных ключевых слов, завершает определение блока операторов, представленного ключевым словом.

## <a name="syntax"></a>Синтаксис

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a>Части

|Отделение|Описание:|
|---|---|
|`End`|Обязательно. Завершает определение программного элемента.|
|`AddHandler`|Обязателен для завершения `AddHandler` метод доступа, начатого соответствующим `AddHandler` инструкции в настраиваемом [оператор Event](event-statement.md).|
|`Class`|Обязателен для завершения определения класса, начатого соответствующим [оператор Class](class-statement.md).|
|`Enum`|Обязателен для завершения определение перечисления начатого соответствующим [оператор Enum](enum-statement.md).|
|`Event`|Обязателен для завершения `Custom` определения события, начатого соответствующим [оператор Event](event-statement.md).|  
|`Function`|Обязателен для завершения `Function` определение процедуры, начатого соответствующим [инструкции Function](function-statement.md). Если при выполнении обнаружена `End Function` инструкции, управление возвращается вызывающему коду.|
|`Get`|Обязателен для завершения `Property` определение процедуры, начатого соответствующим [оператор Get](get-statement.md). Если при выполнении обнаружена `End Get` инструкции, управление возвращается в инструкции, запрашивающего значение свойства.|
|`If`|Обязателен для завершения `If`... `Then`... `Else` определением, начатого соответствующим блока `If` инструкции. См. в разделе [Если... Затем... Оператор Else](if-then-else-statement.md).|
|`Interface`|Обязателен для завершения определения интерфейса начатого соответствующим [Interface-оператор](interface-statement.md).|
|`Module`|Необходимые для завершения определения события, начатого соответствующим [оператор Module](module-statement.md).|
|`Namespace`|Обязателен для завершения определения пространства имен, начатого соответствующим [оператор Namespace](namespace-statement.md).|
|`Operator`|Необходимые для завершения определения оператора, начатого соответствующим [Operator Statement](operator-statement.md).|
|`Property`|Необходимые для завершения определения свойства, начатого соответствующим [Property Statement](property-statement.md).|
|`RaiseEvent`|Обязателен для завершения `RaiseEvent` метод доступа, начатого соответствующим `RaiseEvent` инструкции в настраиваемом [оператор Event](event-statement.md).|
|`RemoveHandler`|Обязателен для завершения `RemoveHandler` метод доступа, начатого соответствующим `RemoveHandler` инструкции в настраиваемом [оператор Event](event-statement.md).|
|`Select`|Обязателен для завершения `Select`... `Case` определением, начатого соответствующим блока `Select` инструкции. См. в разделе [выберите... Оператор выбора](select-case-statement.md).  
|`Set`|Обязателен для завершения `Property` определение процедуры, начатого соответствующим [инструкция Set](set-statement.md). Если при выполнении обнаружена `End Set` инструкции, управление возвращается оператор, который задает значение свойства.  
|`Structure`|Обязателен для завершения определения структуры, начатого соответствующим [оператор Structure](structure-statement.md).  
|`Sub`|Обязателен для завершения `Sub` определение процедуры, начатого соответствующим [оператор Sub](sub-statement.md). Если при выполнении обнаружена `End Sub` инструкции, управление возвращается вызывающему коду.  
|`SyncLock`|Обязателен для завершения `SyncLock` определением, начатого соответствующим блока `SyncLock` инструкции. См. в разделе [оператор SyncLock](synclock-statement.md).  
|`Try`|Обязателен для завершения `Try`... `Catch`... `Finally` определением, начатого соответствующим блока `Try` инструкции. См. в разделе [попробуйте... CATCH... Оператор Finally](try-catch-finally-statement.md).  
|`While`|Обязателен для завершения `While` определение, начатого соответствующим цикла for `While` инструкции. См. в разделе [хотя... Завершить оператор While](while-end-while-statement.md).  
|`With`| Обязателен для завершения `With` определением, начатого соответствующим блока `With` инструкции. См. в разделе [с... Завершить с помощью инструкции](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Директивы

Если предшествует знак номера (`#`), `End` ключевое слово завершает блок предварительной обработки, представленный соответствующей директивы.  

```vb
#End ExternalSource
#End If
#End Region
```

|Отделение|Описание:|
|---|---|
|`#End`|Обязательно. Завершает определение блока предварительной обработки.|
|`ExternalSource`|Обязателен для завершения блока внешнего источника, начатого соответствующим [директива #ExternalSource](../directives/externalsource-directive.md).|
|`If`|Обязателен для завершения блока условной компиляции, начатого соответствующим `#If` директива. См. в разделе [#If... Then... #Else директивы](../directives/if-then-else-directives.md).|
|`Region`|Обязателен для завершения блока региона начатого соответствующим [директива #Region](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Примечания

[Оператор End](end-statement.md), без дополнительных ключевых слов, немедленно прекращает выполнение.

## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

`End` Инструкция без дополнительных ключевых слов, не поддерживается.  
  
## <a name="see-also"></a>См. также

[Оператор End](end-statement.md)

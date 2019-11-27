---
title: Оператор End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343738"
---
# <a name="end-keyword-statement-visual-basic"></a>End \<ключевое слово > (Visual Basic)

Если за ним следует дополнительное ключевое слово, завершает определение блока операторов, представленного этим ключевым словом.

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

|Отделение|Описание|
|---|---|
|`End`|Обязательно. Завершает определение программного элемента.|
|`AddHandler`|Требуется для завершения `AddHandler` метода доступа, начатого соответствующей инструкцией `AddHandler` в пользовательской [инструкции Event](event-statement.md).|
|`Class`|Требуется для завершения определения класса, начатого соответствующим [оператором класса](class-statement.md).|
|`Enum`|Требуется для завершения определения перечисления, начатого соответствующей [инструкцией enum](enum-statement.md).|
|`Event`|Требуется для завершения `Custom` определения события, начатого соответствующей [инструкцией Event](event-statement.md).|  
|`Function`|Требуется для завершения `Function` определения процедуры, начатой соответствующей [инструкцией Function](function-statement.md). Если при выполнении обнаруживается оператор `End Function`, управление возвращается в вызывающий код.|
|`Get`|Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией GET](get-statement.md). Если при выполнении обнаруживается оператор `End Get`, управление возвращается инструкции, запрашивающей значение свойства.|
|`If`|Требуется для завершения `If`...`Then`...`Else` определения блока, начатого соответствующей инструкцией `If`. См. раздел [If... Затем... Else, инструкция](if-then-else-statement.md).|
|`Interface`|Требуется для завершения определения интерфейса, начатого соответствующей [инструкцией интерфейса](interface-statement.md).|
|`Module`|Требуется для завершения определения модуля, начатого соответствующим [оператором модуля](module-statement.md).|
|`Namespace`|Требуется для завершения определения пространства имен, начатого соответствующей [инструкцией Namespace](namespace-statement.md).|
|`Operator`|Требуется для завершения определения оператора, начатого соответствующим [оператором оператора](operator-statement.md).|
|`Property`|Требуется для завершения определения свойства, начатого соответствующим [оператором Property](property-statement.md).|
|`RaiseEvent`|Требуется для завершения `RaiseEvent` метода доступа, начатого соответствующей инструкцией `RaiseEvent` в пользовательской [инструкции Event](event-statement.md).|
|`RemoveHandler`|Требуется для завершения `RemoveHandler` метода доступа, начатого соответствующей инструкцией `RemoveHandler` в пользовательской [инструкции Event](event-statement.md).|
|`Select`|Требуется для завершения `Select`...`Case` определения блока, начатого соответствующей инструкцией `Select`. См. раздел [SELECT... Case, инструкция](select-case-statement.md).  
|`Set`|Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией SET](set-statement.md). Если при выполнении обнаруживается оператор `End Set`, управление возвращается в инструкцию, устанавливая значение свойства.  
|`Structure`|Требуется для завершения определения структуры, начатой соответствующей [инструкцией Structure](structure-statement.md).  
|`Sub`|Требуется для завершения `Sub` определения процедуры, начатой соответствующим [оператором подвыражения](sub-statement.md). Если при выполнении обнаруживается оператор `End Sub`, управление возвращается в вызывающий код.  
|`SyncLock`|Требуется для завершения определения блока `SyncLock`, начатого соответствующей инструкцией `SyncLock`. См. раздел [оператор SyncLock](synclock-statement.md).  
|`Try`|Требуется для завершения `Try`...`Catch`...`Finally` определения блока, начатого соответствующей инструкцией `Try`. См [. раздел try... Перехватить... Оператор finally](try-catch-finally-statement.md).  
|`While`|Требуется для завершения определения цикла `While`, начатого соответствующей инструкцией `While`. См [. раздел while... Конец оператора while](while-end-while-statement.md).  
|`With`| Требуется для завершения определения блока `With`, начатого соответствующей инструкцией `With`. См [. раздел with... Конец оператора](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Директивы

Если перед ним стоит знак решетки (`#`), ключевое слово `End` завершает блок предварительной обработки, представленный соответствующей директивой.  

```vb
#End ExternalSource
#End If
#End Region
```

|Отделение|Описание|
|---|---|
|`#End`|Обязательно. Завершает определение блока предварительной обработки.|
|`ExternalSource`|Требуется для завершения внешнего блока источника, начатого соответствующей [директивой #ExternalSource](../directives/externalsource-directive.md).|
|`If`|Требуется для завершения блока условной компиляции, начатого соответствующей директивой `#If`. См [. #If... Then... #Else директивы](../directives/if-then-else-directives.md).|
|`Region`|Требуется для завершения блока исходного региона, начатого соответствующей [директивой #Region](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Примечания

[Оператор End](end-statement.md)без дополнительного ключевого слова завершает выполнение немедленно.

## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

Инструкция `End` без дополнительного ключевого слова не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Оператор End](end-statement.md)

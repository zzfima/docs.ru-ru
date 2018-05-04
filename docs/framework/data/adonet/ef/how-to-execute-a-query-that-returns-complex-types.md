---
title: Практическое руководство. Выполнение запроса, возвращающего сложные типы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b999033046eb251400f033314ae7eb197a8f110a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Практическое руководство. Выполнение запроса, возвращающего сложные типы
В этом разделе показано выполнение запроса на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)], который возвращает объекты типа сущности, содержащие свойство сложного типа.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1.  Добавить [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Дважды щелкните EDMX-файл для отображения модели в [окне обозревателя моделей](http://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) конструктора сущностей. В области конструктора сущностей выберите `Email` и `Phone` свойства `Contact` типа сущности, а затем щелкните правой кнопкой мыши и выберите **рефакторинг в новый сложный тип**.  
  
4.  Новый сложный тип с выбранным `Email` и `Phone` добавлять свойства к **браузер моделей**. Сложный тип присваивается имя по умолчанию: Переименование типа в тип `EmailPhone` в **свойства** окна. Кроме того, новое свойство `ComplexProperty` добавляется к типу сущности `Contact`. Измените имя свойства на `EmailPhoneComplexType.`  
  
     Сведения о создании и изменении сложных типов с помощью мастера моделей EDM см. в разделе [как: Рефакторинг существующего свойства в свойство сложного типа](http://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) и [как: создавать и изменять сложные типы](http://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется запрос, возвращающий коллекцию `Contact` объектов и отображает два свойства `Contact` объектов: `ContactID` и значения `EmailPhoneComplexType` сложного типа.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]

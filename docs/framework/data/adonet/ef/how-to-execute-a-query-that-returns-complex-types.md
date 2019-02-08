---
title: Как выполнить  выполнить запрос, возвращающий сложные типы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 6c063c9ef6bfde868c773d941ba2107dbaa9ee73
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827127"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Как выполнить  выполнить запрос, возвращающий сложные типы
В этом разделе показано выполнение запроса на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)], который возвращает объекты типа сущности, содержащие свойство сложного типа.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1.  Добавить [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [Как Использовать мастер моделей EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Дважды щелкните EDMX-файл для отображения модели в [окно браузера моделей](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) конструктора сущностей. В области конструктора сущностей выберите `Email` и `Phone` свойства `Contact` тип сущности, а затем щелкните правой кнопкой мыши и выберите **реструктурировать в новый сложный тип**.  
  
4.  Новый сложный тип с выбранными `Email` и `Phone` добавляется свойства **браузер моделей**. Сложному типу присваивается имя по умолчанию: переименовать тип в `EmailPhone` в **свойства** окна. Кроме того, новое свойство `ComplexProperty` добавляется к типу сущности `Contact`. Измените имя свойства на `EmailPhoneComplexType.`  
  
     Сведения о создании и изменении сложных типов с помощью мастера моделей EDM, см. в разделе [как: Реструктурировать существующие свойства в свойство сложного типа](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) и [как: Создавать и изменять сложные типы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется запрос, возвращающий коллекцию `Contact` объектов и отображает два свойства `Contact` объектов: `ContactID` и значения `EmailPhoneComplexType` сложного типа.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]

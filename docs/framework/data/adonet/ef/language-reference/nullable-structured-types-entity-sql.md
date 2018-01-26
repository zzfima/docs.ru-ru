---
title: "Допускающие значения null структурированные типы (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 29b0aa7f6f155de2c55f88b4c796ecc482d1cb84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="nullable-structured-types-entity-sql"></a>Допускающие значения null структурированные типы (Entity SQL)
Экземпляр `null` структурированного типа - несуществующий экземпляр. Это отличается от существующего экземпляра, все свойства которого имеют значения `null`.  
  
 В этом разделе описаны структурированные типы, допускающие значение NULL, с указанием, какие типы допускают значение NULL и какие последовательности программного кода формируют экземпляры `null` структурированных типов, допускающих значение NULL.  
  
## <a name="kinds-of-nullable-structured-types"></a>Разновидности структурированных типов, допускающих значение NULL  
 Существует три разновидности структурированных типов, допускающих значение NULL:  
  
-   Типы строк.  
  
-   Сложные типы.  
  
-   Типы сущностей.  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Шаблоны кода, которые формируют экземпляры NULL структурированных типов  
 В следующем сценарии формируются экземпляры `null`:  
  
-   Формирование `null` как структурированного типа:  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   Приведение базового типа к производному типу:  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   Внешнее соединение по условию FALSE:  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --или  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --или  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   Разыменование ссылки на `null`:  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   Получение значения ANYELEMENT из пустой коллекции:  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   Проверка наличия экземпляров `null` структурированных типов:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

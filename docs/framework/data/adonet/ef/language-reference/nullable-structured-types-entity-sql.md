---
title: "Допускающие значения null структурированные типы (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Допускающие значения null структурированные типы (Entity SQL)
Экземпляр `null` структурированного типа \- несуществующий экземпляр.  Это отличается от существующего экземпляра, все свойства которого имеют значения `null`.  
  
 В этом разделе описаны структурированные типы, допускающие значение NULL, с указанием, какие типы допускают значение NULL и какие последовательности программного кода формируют экземпляры `null` структурированных типов, допускающих значение NULL.  
  
## Разновидности структурированных типов, допускающих значение NULL  
 Существует три разновидности структурированных типов, допускающих значение NULL:  
  
-   Типы строк.  
  
-   Сложные типы.  
  
-   Типы сущностей.  
  
## Шаблоны кода, которые формируют экземпляры NULL структурированных типов  
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
  
     \-\-или  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     \-\-или  
  
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
            Console.WriteLine(“[NULL]”);  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## См. также  
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
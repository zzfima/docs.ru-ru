---
title: "Как выполнить запрос, возвращающий сложные типы | Microsoft Docs"
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
  - "ESQL"
  - "jsharp"
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как выполнить запрос, возвращающий сложные типы
В этом разделе показано выполнение запроса на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)], который возвращает объекты типа сущности, содержащие свойство сложного типа.  
  
### Выполнение кода в этом примере  
  
1.  Добавьте [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832) к проекту и настройте проект на использование [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Для получения дополнительной информации см. [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ru-ru/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Дважды щелкните EDMX\-файл, чтобы вывести модель в [окне браузера моделей](http://msdn.microsoft.com/ru-ru/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) конструктора сущностей.  В области конструктора сущностей выделите свойства `Email` и `Phone` типа сущности `Contact`, затем щелкните правой кнопкой мыши и выберите команду **Реструктурировать в новый сложный тип**.  
  
4.  Новый сложный тип с выбранными свойствами `Email` и `Phone` будет добавлен в **браузер моделей**.  Сложному типу присваивается имя по умолчанию. В окне **Свойства** измените имя типа на `EmailPhone`.  Кроме того, новое свойство `ComplexProperty` добавляется к типу сущности `Contact`.  Измените имя свойства на `EmailPhoneComplexType.`  
  
     Сведения о создании и изменении сложных типов с помощью мастера моделей EDM см. в разделах [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/ru-ru/5b2eb3b3-693d-42cb-b43a-405812d677eb) и [How to: Create and Modify Complex Types](http://msdn.microsoft.com/ru-ru/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## Пример  
 Следующий пример выполняет запрос, который возвращает коллекцию объектов `Contact` и отображает два свойства объектов `Contact` : `ContactID` и значения сложного типа `EmailPhoneComplexType`.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
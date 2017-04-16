---
title: "Концепции сериализации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Концепции сериализации
Для чего нужна сериализация?Двумя наиболее важными причинами являются сохранение состояния объекта в среде хранения, чтобы впоследствии можно было воссоздать точную копию, и отправить объект по значению из одного домена приложения в другой.Например, сериализация используется, чтобы сохранить состояние сеанса в ASP.NET и скопировать объекты в буфер обмена в Windows Forms.Она также используется при удаленном взаимодействии для передачи объектов по значению с одного домена приложения в другой.  
  
## В этом подразделе  
 [Постоянное хранилище](../../../docs/framework/serialization/persistent-storage.md)  
 Содержит информацию о необходимости сериализации объекта.  
  
 [Маршалинг по значению](../../../docs/framework/serialization/marshal-by-value.md)  
 Содержит описание процесса, маршалируемого по значению.  
  
## Связанные подразделы  
 [Двоичная сериализация](../../../docs/framework/serialization/binary-serialization.md)  
 Описывает механизм двоичной сериализации, входящий в среду CLR.  
  
 [Remote Objects](http://msdn.microsoft.com/ru-ru/515686e6-0a8d-42f7-8188-73abede57c58)  
 Описывает различные методы взаимодействия, доступные в платформе .NET Framework для удаленного взаимодействия.  
  
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Описывает механизм сериализации XML и SOAP, входящий в среду CLR.
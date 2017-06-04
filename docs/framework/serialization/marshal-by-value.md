---
title: "Маршалинг по значению | Microsoft Docs"
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
helpviewer_keywords: 
  - "двоичная сериализация, маршалинг по значению"
  - "объекты, маршалируемые по значению"
  - "сериализация, маршалинг по значению"
ms.assetid: ee91e8f0-92e0-4732-8015-d17dee154be1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Маршалинг по значению
Объекты являются допустимыми только в том домене приложения, в котором они были созданы.Любая попытка передать объект как параметр или вернуть его как результат будет завершаться ошибкой, пока объект наследуется от [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) или отмечен как [Serializable](frlrfSystemSerializableAttributeClassTopic).Если объект отмечен как **Serializable**, он будет автоматически сериализован, передан из одного домена приложений в другой, а затем десериализован с целью создания точной копии объекта во втором домене приложения.Этот процесс обычно называют маршалинг по значению.  
  
 Когда объект наследуется от **MarshalByRefObject**, из одного домена приложения в другой передается ссылка на объект, а не сам объект.Также можно отметить объект, наследуемый от **MarshalByRefObject**, как **Serializable**.Когда этот объект используется для удаленного взаимодействия, модуль форматирования, отвечающий за сериализацию и предварительно настроенный с помощью суррогатного селектора \([SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)\), берет на себя управление процессом сериализации и заменяет все объекты, унаследованные от [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) с помощью прокси.При отсутствии [SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic) архитектура сериализации следует стандартным правилам сериализации, представленным в разделе [Этапы процесса сериализации](../../../docs/framework/serialization/steps-in-the-serialization-process.md).  
  
## См. также  
 [Концепции сериализации](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/ru-ru/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)
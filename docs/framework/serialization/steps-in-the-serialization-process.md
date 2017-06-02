---
title: "Этапы процесса сериализации | Microsoft Docs"
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
  - "двоичная сериализация, шаги"
  - "сериализация, шаги"
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Этапы процесса сериализации
При вызове метода [Serialize](frlrfSystemRuntimeSerializationFormatterClassSerializeTopic) для [модуля форматирования](frlrfSystemRuntimeSerializationFormatterClassTopic) сериализация объекта осуществляется в следующей последовательности:  
  
-   Выполняется проверка для определения, имеется ли у модуля форматирования суррогатный селектор.Если такой селектор обнаружен, выполняется проверка, обрабатывает ли суррогатный селектор объекты указанного типа.Если селектор обрабатывает объекты такого типа, для суррогатного селектора вызывается **ISerializable.GetObjectData**.  
  
-   Если суррогатный селектор отсутствует или не обрабатывает объекты такого типа, объект проверяется на наличие атрибута [Serializable](frlrfSystemSerializableAttributeClassTopic).Если такой атрибут отсутствует, выдается [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic).  
  
-   Если объект отмечен правильным атрибутом, проверяется, реализует ли объект интерфейс [ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic).Если объект такой интерфейс реализует, для него вызывается [GetObjectData](frlrfSystemRuntimeSerializationISerializableClassGetObjectDataTopic).  
  
-   Если объект не реализует интерфейс **ISerializable**, используется политика сериализации по умолчанию, при которой сериализуются все поля, не отмеченные [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic).  
  
## См. также  
 [Двоичная сериализация](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/ru-ru/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)
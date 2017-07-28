---
title: "Управление сериализацией и десериализацией с помощью SerializationBinder | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Управление сериализацией и десериализацией с помощью SerializationBinder
При сериализации модуль форматирования передает сведения, необходимые для создания экземпляра объекта правильных типа и версии.  Эти сведения обычно содержат полное имя типа и имя сборки объекта.  По умолчанию с помощью этих сведений операция десериализации создает экземпляр такого же объекта.  Некоторым пользователям может понадобиться возможность выбирать классы для сериализации и десериализации, поскольку исходный класс может отсутствовать на компьютере, где выполняется десериализация, быть перемещенным в другую сборку либо на сервере и клиенте могут требоваться разные версии класса.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Использование средства привязки сериализации](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Эта функция доступна только при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## Использование класса SerializationBinder  
 Класс <xref:System.Runtime.Serialization.SerializationBinder> является абстрактным классом, который используется для управления фактическими типами, применяемыми при сериализации и десериализации.  Чтобы управлять типами, используемыми при сериализации и десериализации, нужно создать класс, производный от класса <xref:System.Runtime.Serialization.SerializationBinder>, и переопределить методы <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False&autoUpgrade=True и <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False&autoUpgrade=True.  Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False&autoUpgrade=True принимает объект <xref:System.Type> и возвращает имя типа и сборки.  Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False&autoUpgrade=True принимает имя сборки и типа и возвращает объект <xref:System.Type>.  
  
## См. также  
 [Сериализация и десериализация](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)   
 [Использование средства привязки сериализации](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
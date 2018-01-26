---
title: "Управление сериализацией и десериализацией с помощью SerializationBinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba2140459c0b571e9b35824d3dba274e8447ac40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Управление сериализацией и десериализацией с помощью SerializationBinder
При сериализации модуль форматирования передает сведения, необходимые для создания экземпляра объекта правильных типа и версии. Эти сведения обычно содержат полное имя типа и имя сборки объекта. По умолчанию с помощью этих сведений операция десериализации создает экземпляр такого же объекта. Некоторым пользователям может понадобиться возможность выбирать классы для сериализации и десериализации, поскольку исходный класс может отсутствовать на компьютере, где выполняется десериализация, быть перемещенным в другую сборку либо на сервере и клиенте могут требоваться разные версии класса. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Использование средства привязки сериализации](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Эта функция доступна только при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Использование класса SerializationBinder  
 Класс <xref:System.Runtime.Serialization.SerializationBinder> является абстрактным классом, который используется для управления фактическими типами, применяемыми при сериализации и десериализации. Чтобы управлять типами, используемыми при сериализации и десериализации, нужно создать класс, производный от класса <xref:System.Runtime.Serialization.SerializationBinder>, и переопределить методы <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> и <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> принимает объект <xref:System.Type> и возвращает имя типа и сборки. Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> принимает имя сборки и типа и возвращает объект <xref:System.Type>.  
  
## <a name="see-also"></a>См. также  
 [Сериализация и десериализация](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Использование средства привязки сериализации](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)

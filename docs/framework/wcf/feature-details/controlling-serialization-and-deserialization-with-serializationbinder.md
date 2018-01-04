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
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="28dd8-102">Управление сериализацией и десериализацией с помощью SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="28dd8-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="28dd8-103">При сериализации модуль форматирования передает сведения, необходимые для создания экземпляра объекта правильных типа и версии.</span><span class="sxs-lookup"><span data-stu-id="28dd8-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="28dd8-104">Эти сведения обычно содержат полное имя типа и имя сборки объекта.</span><span class="sxs-lookup"><span data-stu-id="28dd8-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="28dd8-105">По умолчанию с помощью этих сведений операция десериализации создает экземпляр такого же объекта.</span><span class="sxs-lookup"><span data-stu-id="28dd8-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="28dd8-106">Некоторым пользователям может понадобиться возможность выбирать классы для сериализации и десериализации, поскольку исходный класс может отсутствовать на компьютере, где выполняется десериализация, быть перемещенным в другую сборку либо на сервере и клиенте могут требоваться разные версии класса.</span><span class="sxs-lookup"><span data-stu-id="28dd8-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="28dd8-107">[Использование средства привязки сериализации](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span><span class="sxs-lookup"><span data-stu-id="28dd8-107"> [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="28dd8-108">Эта функция доступна только при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="28dd8-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="28dd8-109">Использование класса SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="28dd8-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="28dd8-110">Класс <xref:System.Runtime.Serialization.SerializationBinder> является абстрактным классом, который используется для управления фактическими типами, применяемыми при сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="28dd8-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="28dd8-111">Чтобы управлять типами, используемыми при сериализации и десериализации, нужно создать класс, производный от класса <xref:System.Runtime.Serialization.SerializationBinder>, и переопределить методы <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> и <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>.</span><span class="sxs-lookup"><span data-stu-id="28dd8-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="28dd8-112">Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> принимает объект <xref:System.Type> и возвращает имя типа и сборки.</span><span class="sxs-lookup"><span data-stu-id="28dd8-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="28dd8-113">Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> принимает имя сборки и типа и возвращает объект <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="28dd8-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28dd8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="28dd8-114">See Also</span></span>  
 [<span data-ttu-id="28dd8-115">Сериализация и десериализация</span><span class="sxs-lookup"><span data-stu-id="28dd8-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="28dd8-116">Использование средства привязки сериализации</span><span class="sxs-lookup"><span data-stu-id="28dd8-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)

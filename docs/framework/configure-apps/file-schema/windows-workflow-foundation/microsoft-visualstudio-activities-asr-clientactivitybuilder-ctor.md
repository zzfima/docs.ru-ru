---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="805a4-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="805a4-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="805a4-103">Создает экземпляр [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) класса.</span><span class="sxs-lookup"><span data-stu-id="805a4-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="805a4-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="805a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="805a4-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="805a4-106">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="805a4-106">Parameter Values</span></span>  
 <span data-ttu-id="805a4-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="805a4-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="805a4-108">описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="805a4-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="805a4-109">Значение этого параметра не должно быть **null**.</span><span class="sxs-lookup"><span data-stu-id="805a4-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="805a4-110">Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="805a4-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="805a4-111">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="805a4-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="805a4-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="805a4-112">*configurationName*</span></span>  
  
 <span data-ttu-id="805a4-113">указывает имя конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="805a4-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="805a4-114">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="805a4-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="805a4-115">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="805a4-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="805a4-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="805a4-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="805a4-117">указывает пространство имен службы для операции.</span><span class="sxs-lookup"><span data-stu-id="805a4-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="805a4-118">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="805a4-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="805a4-119">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="805a4-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805a4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="805a4-120">See Also</span></span>  
 [<span data-ttu-id="805a4-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="805a4-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

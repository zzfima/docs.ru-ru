---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b73274a09ae748cdf1ee33c885de86b1f52c105
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="d4e44-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="d4e44-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="d4e44-103">Создает экземпляр [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) класса.</span><span class="sxs-lookup"><span data-stu-id="d4e44-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4e44-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4e44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4e44-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="d4e44-106">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="d4e44-106">Parameter Values</span></span>  
 <span data-ttu-id="d4e44-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="d4e44-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="d4e44-108">описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="d4e44-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="d4e44-109">Значение этого параметра не должно быть **null**.</span><span class="sxs-lookup"><span data-stu-id="d4e44-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="d4e44-110">Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="d4e44-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="d4e44-111">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="d4e44-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="d4e44-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="d4e44-112">*configurationName*</span></span>  
  
 <span data-ttu-id="d4e44-113">указывает имя конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d4e44-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="d4e44-114">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="d4e44-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="d4e44-115">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="d4e44-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="d4e44-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="d4e44-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="d4e44-117">указывает пространство имен службы для операции.</span><span class="sxs-lookup"><span data-stu-id="d4e44-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="d4e44-118">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="d4e44-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="d4e44-119">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="d4e44-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e44-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d4e44-120">See Also</span></span>  
 [<span data-ttu-id="d4e44-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="d4e44-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

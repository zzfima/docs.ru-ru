---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: aca5a6ad07d96e08203e9e1cad7dec632035caf0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755504"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="23cb4-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="23cb4-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="23cb4-103">Создает экземпляр [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) класса.</span><span class="sxs-lookup"><span data-stu-id="23cb4-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23cb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23cb4-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23cb4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="23cb4-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="23cb4-106">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="23cb4-106">Parameter Values</span></span>  
 <span data-ttu-id="23cb4-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="23cb4-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="23cb4-108">описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="23cb4-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="23cb4-109">Значение этого параметра не должно быть **null**.</span><span class="sxs-lookup"><span data-stu-id="23cb4-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="23cb4-110">Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="23cb4-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="23cb4-111">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="23cb4-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="23cb4-112">*ConfigurationName*</span><span class="sxs-lookup"><span data-stu-id="23cb4-112">*configurationName*</span></span>  
  
 <span data-ttu-id="23cb4-113">указывает имя конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="23cb4-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="23cb4-114">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="23cb4-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="23cb4-115">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="23cb4-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="23cb4-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="23cb4-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="23cb4-117">указывает пространство имен службы для операции.</span><span class="sxs-lookup"><span data-stu-id="23cb4-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="23cb4-118">Значение этого параметра не должно быть либо **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="23cb4-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="23cb4-119">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="23cb4-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23cb4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="23cb4-120">See Also</span></span>  
 [<span data-ttu-id="23cb4-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="23cb4-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

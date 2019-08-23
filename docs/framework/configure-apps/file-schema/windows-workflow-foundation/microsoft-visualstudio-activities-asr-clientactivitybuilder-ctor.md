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
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947619"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="fab0e-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="fab0e-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="fab0e-103">Создает экземпляр класса [Microsoft. VisualStudio. activitys. ASR. клиентактивитибуилдер](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .</span><span class="sxs-lookup"><span data-stu-id="fab0e-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fab0e-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fab0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fab0e-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="fab0e-106">Значения параметров</span><span class="sxs-lookup"><span data-stu-id="fab0e-106">Parameter Values</span></span>  
 <span data-ttu-id="fab0e-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="fab0e-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="fab0e-108">описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="fab0e-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="fab0e-109">Значение этого параметра не должно быть **равно NULL**.</span><span class="sxs-lookup"><span data-stu-id="fab0e-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="fab0e-110">Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.</span><span class="sxs-lookup"><span data-stu-id="fab0e-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="fab0e-111">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="fab0e-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="fab0e-112">*Указав*</span><span class="sxs-lookup"><span data-stu-id="fab0e-112">*configurationName*</span></span>  
  
 <span data-ttu-id="fab0e-113">указывает имя конфигурации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fab0e-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="fab0e-114">Значение этого параметра не должно быть **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="fab0e-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="fab0e-115">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="fab0e-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="fab0e-116">*проксинамеспаце*</span><span class="sxs-lookup"><span data-stu-id="fab0e-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="fab0e-117">указывает пространство имен службы для операции.</span><span class="sxs-lookup"><span data-stu-id="fab0e-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="fab0e-118">Значение этого параметра не должно быть **null** или пустым.</span><span class="sxs-lookup"><span data-stu-id="fab0e-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="fab0e-119">Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.</span><span class="sxs-lookup"><span data-stu-id="fab0e-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab0e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fab0e-120">See also</span></span>

- [<span data-ttu-id="fab0e-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="fab0e-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)

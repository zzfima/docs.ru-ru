---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b6838c6ce98e0d373a45c136b12bdedbd8c9eb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="eca97-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="eca97-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="eca97-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="eca97-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eca97-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eca97-105">Методы</span><span class="sxs-lookup"><span data-stu-id="eca97-105">Methods</span></span>  
 <span data-ttu-id="eca97-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="eca97-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eca97-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="eca97-107">Properties</span></span>  
 <span data-ttu-id="eca97-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="eca97-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="eca97-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="eca97-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="eca97-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="eca97-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="eca97-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eca97-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eca97-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="eca97-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eca97-113">Требования</span><span class="sxs-lookup"><span data-stu-id="eca97-113">Requirements</span></span>  
  
|<span data-ttu-id="eca97-114">MOF</span><span class="sxs-lookup"><span data-stu-id="eca97-114">MOF</span></span>|<span data-ttu-id="eca97-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eca97-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eca97-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="eca97-116">Namespace</span></span>|<span data-ttu-id="eca97-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="eca97-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eca97-118">См. также</span><span class="sxs-lookup"><span data-stu-id="eca97-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

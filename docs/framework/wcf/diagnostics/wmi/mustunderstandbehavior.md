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
ms.openlocfilehash: 40075acb2a098c98b4cd0ab35f213981c09f8486
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="735ff-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="735ff-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="735ff-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="735ff-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="735ff-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="735ff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="735ff-105">Methods</span></span>  
 <span data-ttu-id="735ff-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="735ff-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="735ff-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="735ff-107">Properties</span></span>  
 <span data-ttu-id="735ff-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="735ff-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="735ff-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="735ff-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="735ff-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="735ff-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="735ff-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="735ff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="735ff-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="735ff-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735ff-113">Требования</span><span class="sxs-lookup"><span data-stu-id="735ff-113">Requirements</span></span>  
  
|<span data-ttu-id="735ff-114">MOF</span><span class="sxs-lookup"><span data-stu-id="735ff-114">MOF</span></span>|<span data-ttu-id="735ff-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="735ff-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="735ff-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="735ff-116">Namespace</span></span>|<span data-ttu-id="735ff-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="735ff-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="735ff-118">См. также</span><span class="sxs-lookup"><span data-stu-id="735ff-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

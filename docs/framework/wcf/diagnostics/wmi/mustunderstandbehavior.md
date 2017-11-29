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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dca98f1d8d5f868285ecf11c01122f795ee6cfd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="02a49-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="02a49-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="02a49-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="02a49-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02a49-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="02a49-105">Методы</span><span class="sxs-lookup"><span data-stu-id="02a49-105">Methods</span></span>  
 <span data-ttu-id="02a49-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="02a49-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="02a49-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="02a49-107">Properties</span></span>  
 <span data-ttu-id="02a49-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="02a49-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="02a49-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="02a49-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="02a49-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="02a49-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="02a49-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="02a49-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02a49-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="02a49-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a49-113">Требования</span><span class="sxs-lookup"><span data-stu-id="02a49-113">Requirements</span></span>  
  
|<span data-ttu-id="02a49-114">MOF</span><span class="sxs-lookup"><span data-stu-id="02a49-114">MOF</span></span>|<span data-ttu-id="02a49-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="02a49-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="02a49-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="02a49-116">Namespace</span></span>|<span data-ttu-id="02a49-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="02a49-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02a49-118">См. также</span><span class="sxs-lookup"><span data-stu-id="02a49-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

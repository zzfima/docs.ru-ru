---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 14150a992130e9ed4734c950d4ed92f1bbd3206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485561"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="c5f30-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="c5f30-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="c5f30-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="c5f30-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5f30-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c5f30-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c5f30-105">Methods</span></span>  
 <span data-ttu-id="c5f30-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c5f30-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c5f30-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c5f30-107">Properties</span></span>  
 <span data-ttu-id="c5f30-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c5f30-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="c5f30-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="c5f30-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="c5f30-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c5f30-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5f30-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c5f30-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5f30-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="c5f30-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f30-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c5f30-113">Requirements</span></span>  
  
|<span data-ttu-id="c5f30-114">MOF</span><span class="sxs-lookup"><span data-stu-id="c5f30-114">MOF</span></span>|<span data-ttu-id="c5f30-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c5f30-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c5f30-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c5f30-116">Namespace</span></span>|<span data-ttu-id="c5f30-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c5f30-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5f30-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f30-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

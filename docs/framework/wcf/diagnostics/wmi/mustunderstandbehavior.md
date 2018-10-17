---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371800"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="e95ce-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="e95ce-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="e95ce-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="e95ce-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e95ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e95ce-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e95ce-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e95ce-105">Methods</span></span>  
 <span data-ttu-id="e95ce-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e95ce-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e95ce-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e95ce-107">Properties</span></span>  
 <span data-ttu-id="e95ce-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="e95ce-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="e95ce-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="e95ce-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="e95ce-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="e95ce-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e95ce-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e95ce-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e95ce-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="e95ce-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e95ce-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e95ce-113">Requirements</span></span>  
  
|<span data-ttu-id="e95ce-114">MOF</span><span class="sxs-lookup"><span data-stu-id="e95ce-114">MOF</span></span>|<span data-ttu-id="e95ce-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e95ce-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e95ce-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e95ce-116">Namespace</span></span>|<span data-ttu-id="e95ce-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e95ce-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e95ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e95ce-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

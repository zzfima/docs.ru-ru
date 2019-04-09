---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165481"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="845b3-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="845b3-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="845b3-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="845b3-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="845b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="845b3-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="845b3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="845b3-105">Methods</span></span>  
 <span data-ttu-id="845b3-106">Класс MustUnderstandBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="845b3-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="845b3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="845b3-107">Properties</span></span>  
 <span data-ttu-id="845b3-108">Класс MustUnderstandBehavior содержит следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="845b3-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="845b3-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="845b3-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="845b3-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="845b3-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="845b3-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="845b3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="845b3-112">Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.</span><span class="sxs-lookup"><span data-stu-id="845b3-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="845b3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="845b3-113">Requirements</span></span>  
  
|<span data-ttu-id="845b3-114">MOF</span><span class="sxs-lookup"><span data-stu-id="845b3-114">MOF</span></span>|<span data-ttu-id="845b3-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="845b3-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="845b3-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="845b3-116">Namespace</span></span>|<span data-ttu-id="845b3-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="845b3-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="845b3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="845b3-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>

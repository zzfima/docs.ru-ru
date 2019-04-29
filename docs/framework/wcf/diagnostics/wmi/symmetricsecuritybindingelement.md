---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956719"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="777e4-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="777e4-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="777e4-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="777e4-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="777e4-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="777e4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="777e4-105">Methods</span></span>  
 <span data-ttu-id="777e4-106">Класс SymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="777e4-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="777e4-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="777e4-107">Properties</span></span>  
 <span data-ttu-id="777e4-108">Класс SymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="777e4-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="777e4-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="777e4-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="777e4-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="777e4-110">Data type: string</span></span>  
  
 <span data-ttu-id="777e4-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="777e4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="777e4-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="777e4-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="777e4-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="777e4-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="777e4-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="777e4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="777e4-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="777e4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="777e4-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="777e4-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="777e4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="777e4-117">Requirements</span></span>  
  
|<span data-ttu-id="777e4-118">MOF</span><span class="sxs-lookup"><span data-stu-id="777e4-118">MOF</span></span>|<span data-ttu-id="777e4-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="777e4-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="777e4-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="777e4-120">Namespace</span></span>|<span data-ttu-id="777e4-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="777e4-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="777e4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="777e4-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

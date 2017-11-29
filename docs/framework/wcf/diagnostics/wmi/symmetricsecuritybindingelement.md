---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="23a89-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="23a89-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="23a89-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="23a89-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23a89-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="23a89-105">Методы</span><span class="sxs-lookup"><span data-stu-id="23a89-105">Methods</span></span>  
 <span data-ttu-id="23a89-106">Класс SymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="23a89-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="23a89-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="23a89-107">Properties</span></span>  
 <span data-ttu-id="23a89-108">Класс SymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="23a89-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="23a89-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="23a89-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="23a89-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="23a89-110">Data type: string</span></span>  
  
 <span data-ttu-id="23a89-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="23a89-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="23a89-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="23a89-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="23a89-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="23a89-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="23a89-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="23a89-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="23a89-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="23a89-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="23a89-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="23a89-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23a89-117">Требования</span><span class="sxs-lookup"><span data-stu-id="23a89-117">Requirements</span></span>  
  
|<span data-ttu-id="23a89-118">MOF</span><span class="sxs-lookup"><span data-stu-id="23a89-118">MOF</span></span>|<span data-ttu-id="23a89-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="23a89-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="23a89-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="23a89-120">Namespace</span></span>|<span data-ttu-id="23a89-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="23a89-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23a89-122">См. также</span><span class="sxs-lookup"><span data-stu-id="23a89-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

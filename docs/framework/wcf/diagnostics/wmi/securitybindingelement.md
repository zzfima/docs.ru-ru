---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975563"
---
# <a name="securitybindingelement"></a><span data-ttu-id="35a7e-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="35a7e-102">SecurityBindingElement</span></span>
<span data-ttu-id="35a7e-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="35a7e-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35a7e-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="35a7e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="35a7e-105">Methods</span></span>  
 <span data-ttu-id="35a7e-106">Класс SecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="35a7e-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="35a7e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="35a7e-107">Properties</span></span>  
 <span data-ttu-id="35a7e-108">Класс SecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="35a7e-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="35a7e-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="35a7e-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="35a7e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="35a7e-110">Data type: string</span></span>  
  
 <span data-ttu-id="35a7e-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-112">Задает алгоритмы, используемые в сочетании с привязкой.</span><span class="sxs-lookup"><span data-stu-id="35a7e-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="35a7e-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="35a7e-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="35a7e-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="35a7e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="35a7e-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-116">Логическое значение, указывающее, будет ли в каждое сообщение вноситься метка времени.</span><span class="sxs-lookup"><span data-stu-id="35a7e-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="35a7e-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="35a7e-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="35a7e-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="35a7e-118">Data type: string</span></span>  
  
 <span data-ttu-id="35a7e-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-120">Источник энтропии, используемый для создания ключей.</span><span class="sxs-lookup"><span data-stu-id="35a7e-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="35a7e-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="35a7e-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="35a7e-122">Тип данных: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="35a7e-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="35a7e-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-124">Свойства безопасности для локальной службы, соответствующие данной привязке.</span><span class="sxs-lookup"><span data-stu-id="35a7e-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="35a7e-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="35a7e-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="35a7e-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="35a7e-126">Data type: string</span></span>  
  
 <span data-ttu-id="35a7e-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-128">Версия, используемая для безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="35a7e-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="35a7e-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="35a7e-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="35a7e-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="35a7e-130">Data type: string</span></span>  
  
 <span data-ttu-id="35a7e-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="35a7e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35a7e-132">Порядок элементов в заголовке безопасности для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="35a7e-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a7e-133">Требования</span><span class="sxs-lookup"><span data-stu-id="35a7e-133">Requirements</span></span>  
  
|<span data-ttu-id="35a7e-134">MOF</span><span class="sxs-lookup"><span data-stu-id="35a7e-134">MOF</span></span>|<span data-ttu-id="35a7e-135">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="35a7e-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="35a7e-136">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="35a7e-136">Namespace</span></span>|<span data-ttu-id="35a7e-137">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="35a7e-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35a7e-138">См. также</span><span class="sxs-lookup"><span data-stu-id="35a7e-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>

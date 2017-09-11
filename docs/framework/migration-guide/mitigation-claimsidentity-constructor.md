---
title: "Устранение рисков. Конструктор ClaimsIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="2c5f8-102">Устранение рисков. Конструктор ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="2c5f8-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="2c5f8-103">Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] изменен способ задания конструктором <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> свойства <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="2c5f8-104">Если аргумент <xref:System.Security.Principal.IIdentity> является объектом <xref:System.Security.Claims.ClaimsIdentity>, а свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> этого объекта <xref:System.Security.Claims.ClaimsIdentity> не равно `null`, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> присоединяется с помощью метода <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="2c5f8-105">В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> присоединяется в качестве существующей ссылки.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2c5f8-106">Последствия</span><span class="sxs-lookup"><span data-stu-id="2c5f8-106">Impact</span></span>  
 <span data-ttu-id="2c5f8-107">Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> нового объекта <xref:System.Security.Claims.ClaimsIdentity> не равно свойству <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> аргумента <xref:System.Security.Principal.IIdentity> конструктора.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="2c5f8-108">В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версиях они были равны.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="2c5f8-109">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="2c5f8-109">Mitigation</span></span>  
 <span data-ttu-id="2c5f8-110">Если такое поведение нежелательно, можно восстановить прежнее поведение, задав переключателю `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` в файле конфигурации приложения значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2c5f8-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="2c5f8-111">Для этого требуется добавить следующую информацию в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла web.config:</span><span class="sxs-lookup"><span data-stu-id="2c5f8-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c5f8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2c5f8-112">See Also</span></span>  
 [<span data-ttu-id="2c5f8-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="2c5f8-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)


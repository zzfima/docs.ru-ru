---
title: "Устранение рисков. MemberDescriptor.Equals"
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
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="3006c-102">Устранение рисков. MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="3006c-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="3006c-103">Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], изменилась реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="3006c-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="3006c-104">Поскольку методы `System.ComponentModel.EventDescriptor.Equals` и `System.ComponentModel.PropertyDescriptor.Equals` наследуют реализацию базового класса, изменение на них также влияет.</span><span class="sxs-lookup"><span data-stu-id="3006c-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="3006c-105">В приложениях, предназначенных для версий платформы .NET Framework до [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], часть теста на равенство в методе <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> неверно сравнивала свойство <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> одного объекта со свойством <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> другого.</span><span class="sxs-lookup"><span data-stu-id="3006c-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="3006c-106">Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], метод <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> сравнивает свойство <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> двух объектов.</span><span class="sxs-lookup"><span data-stu-id="3006c-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3006c-107">Последствия</span><span class="sxs-lookup"><span data-stu-id="3006c-107">Impact</span></span>  
 <span data-ttu-id="3006c-108">Это изменение правильно реализует проверку равенства для объектов <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> и должно иметь минимальное влияние.</span><span class="sxs-lookup"><span data-stu-id="3006c-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="3006c-109">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="3006c-109">Mitigation</span></span>  
 <span data-ttu-id="3006c-110">Доступны два решения, если ваше приложение предназначено для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии .NET Framework и зависит от метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, который иногда возвращает `false` при эквивалентных дескрипторах элементов.</span><span class="sxs-lookup"><span data-stu-id="3006c-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="3006c-111">Можно отказаться от этого изменения без модификации исходного кода, добавив следующий код в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:</span><span class="sxs-lookup"><span data-stu-id="3006c-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="3006c-112">Можно изменить исходный код для восстановления предыдущего поведения, сравнивая вручную свойства <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> и <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> после вызова метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, как делает приведенный ниже фрагмент кода.</span><span class="sxs-lookup"><span data-stu-id="3006c-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
    ```csharp  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
    ```  
  
    ```  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
    ```  
  
 <span data-ttu-id="3006c-113">Для приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, можно включить это изменение, добавив следующее значение в файл app.config:</span><span class="sxs-lookup"><span data-stu-id="3006c-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3006c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3006c-114">See Also</span></span>  
 <span data-ttu-id="3006c-115">[Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="3006c-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="3006c-116">Совместимость приложений в 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3006c-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)


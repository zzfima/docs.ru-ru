---
title: "Устранение рисков. MemberDescriptor.Equals | Документация Майкрософт"
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
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 409f06f4dfbe7be50dd2c487e49d3d4d8a477539
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-memberdescriptorequals"></a>Устранение рисков. MemberDescriptor.Equals
Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> изменилась. Поскольку методы `System.ComponentModel.EventDescriptor.Equals` и `System.ComponentModel.PropertyDescriptor.Equals` наследуют реализацию базового класса, изменение на них также влияет.  
  
 В приложениях, предназначенных для версий платформы .NET Framework до [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], часть теста на равенство в методе <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> неверно сравнивала свойство <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> одного объекта со свойством <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> другого. Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], метод <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> сравнивает свойство <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> двух объектов.  
  
## <a name="impact"></a>Последствия  
 Это изменение правильно реализует проверку равенства для объектов <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> и должно иметь минимальное влияние.  
  
## <a name="mitigation"></a>Уменьшение  
 Доступны два решения, если ваше приложение предназначено для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии .NET Framework и зависит от метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, который иногда возвращает `false` при эквивалентных дескрипторах элементов.  
  
-   Можно отказаться от этого изменения без модификации исходного кода, добавив следующий код в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
    ```xml  
  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
  
    ```  
  
-   Можно изменить исходный код для восстановления предыдущего поведения, сравнивая вручную свойства <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> и <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> после вызова метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, как делает следующий фрагмент кода.  
  
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
  
 Для приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, можно включить это изменение, добавив следующее значение в файл app.config:  
  
```xml  
  
<runtime>  
    \<AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)   
 [Совместимость приложений в 4.6.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

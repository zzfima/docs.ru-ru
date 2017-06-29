---
title: "Вопросы безопасности в порождаемом отражении | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- partially trusted code
- emitting dynamic assemblies, security
- reflection emit, security
- reflection emit, partial trust scenarios
- partial trust,emitting dynamic methods
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- dynamic assemblies, security
ms.assetid: 0f8bf8fa-b993-478f-87ab-1a1a7976d298
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: 5d2d814989564dfd4c2d49ebb4b44e5964cf031f
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="security-issues-in-reflection-emit"></a>Вопросы безопасности в порождаемом отражении
Платформа [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] предоставляет три способа создания кода MSIL, с каждым из которых связаны определенные вопросы безопасности.  
  
-   [Динамические сборки](#Dynamic_Assemblies)  
  
-   [Анонимно размещенные динамические методы](#Anonymously_Hosted_Dynamic_Methods)  
  
-   [Динамические методы, связанные с существующими сборками](#Dynamic_Methods_Associated_with_Existing_Assemblies)  
  
 Независимо от способа создания динамического кода для его выполнения необходимы все разрешения, которые требуются типам и методам, используемым этим кодом.  
  
> [!NOTE]
>  Разрешения, необходимые для отражения и порождения кода, изменялись в последующих выпусках [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Подробнее см. в подразделе [Сведения о версиях](#Version_Information) далее в этом разделе.  
  
<a name="Dynamic_Assemblies"></a>   
## <a name="dynamic-assemblies"></a>Динамические сборки  
 Динамические сборки создаются с помощью перегрузок метода <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>. Большинство перегрузок этого метода не рекомендуется использовать в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], так как политика безопасности на уровне компьютера больше не используется. (См. раздел [Изменения системы безопасности](../../../docs/framework/security/security-changes.md).) Остальные перегрузки могут выполняться из любого кода независимо от уровня доверия. Эти перегрузки делятся на две группы: те, которые определяют список атрибутов, применяемых к динамической сборке при ее создании, и те, которые этого не делают. Если не указать модель прозрачности для сборки, применив атрибут <xref:System.Security.SecurityRulesAttribute> при ее создании, эта модель наследуется от порождающей сборки.  
  
> [!NOTE]
>  Атрибуты, применяемые к динамической сборке после ее создания с помощью метода <xref:System.Reflection.Emit.AssemblyBuilder.SetCustomAttribute%2A>, не действуют, пока сборка не будет сохранена на диск и повторно загружена в память.  
  
 Код в динамической сборке может получать доступ к видимым типам и членам в других сборках.  
  
> [!NOTE]
>  Динамические сборки не используют флаги <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> и <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, разрешающие динамическим методам получать доступ к закрытым типам и членам.  
  
 Временные динамические сборки создаются в памяти и никогда не сохраняются на диск, поэтому им не требуются разрешения на доступ к файлам. Для сохранения динамической сборки на диск требуется разрешение <xref:System.Security.Permissions.FileIOPermission> с соответствующими флагами.  
  
### <a name="generating-dynamic-assemblies-from-partially-trusted-code"></a>Создание динамических сборок из частично доверенного кода  
 Рассмотрим условия, в которых сборка с разрешениями на доступ к Интернету может создавать временную динамическую сборку и выполнять ее код.  
  
-   Динамическая сборка использует только открытые типы и члены других сборок.  
  
-   Разрешения, необходимые для этих типов и членов, включаются в набор прав сборки с частичным доверием.  
  
-   Сборка не сохраняется на диск.  
  
-   Отладочные символы не создаются (наборы разрешений `Internet` и `LocalIntranet` не включают необходимые разрешения).  
  
<a name="Anonymously_Hosted_Dynamic_Methods"></a>   
## <a name="anonymously-hosted-dynamic-methods"></a>Анонимно размещенные динамические методы  
 Анонимно размещенные динамические методы создаются с помощью двух конструкторов <xref:System.Reflection.Emit.DynamicMethod>, которые не указывают связанный тип или модуль, <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%29> и <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>. Эти конструкторы размещают динамические методы в предоставляемой системой сборке, которая является полностью доверенной и прозрачный для системы безопасности. Для использования этих конструкторов или порождения кода для динамических методов разрешения не требуются.  
  
 Вместо этого при создании анонимно размещаемых динамических методов записывается стек вызовов. При создании метода требования безопасности предъявляются к записанному стеку вызовов.  
  
> [!NOTE]
>  Концептуально требования предъявляются во время создания метода. То есть требования могут предъявляться при порождении каждой инструкции MSIL. В текущей реализации все требования предъявляются при вызове метода <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A?displayProperty=fullName> или JIT-компилятора, если метод вызывается без вызова <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  
  
 Если домен приложения допускает такое поведение, анонимно размещенные динамические методы могут пропускать проверки видимости JIT-компилятора, однако действует следующее ограничение: закрытые типы и члены, к которым получает доступ анонимно размещенный динамический метод, должны находиться в сборках, наборы прав которых идентичны набору прав порождающего стека вызовов или являются его подмножествами. Эта ограниченная возможность пропускать проверки видимости JIT доступна, если домен приложения предоставляет разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>.  
  
-   Если метод использует только открытые типы и члены, во время его создания никакие разрешения не требуются.  
  
-   Если вы указываете, что проверки видимости JIT следует пропустить, требование, предъявляемое при создании метода, включает разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> и набор прав сборки, содержащей закрытый член, к которому осуществляется доступ.  
  
 Так как учитывается набор прав закрытого члена, частично доверенный код, которому предоставлено разрешение <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, не может повысить свои привилегии путем выполнения закрытых членов доверенных сборок.  
  
 Как и для любого другого порожденного кода, для выполнения этого динамического метода необходимы те же разрешения, которые требуются методам, используемым этим динамическим методом.  
  
 Системная сборка, в которой размещаются анонимно размещенные динамические методы, использует модель прозрачности <xref:System.Security.SecurityRuleSet.Level1?displayProperty=fullName>, то есть модель, которая использовалась в .NET Framework до версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 Дополнительные сведения см. в описании класса <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-anonymously-hosted-dynamic-methods-from-partially-trusted-code"></a>Создание анонимно размещенных динамических методов из частично доверенного кода  
 Рассмотрим условия, в которых сборка с разрешениями на доступ к Интернету может создавать анонимно размещенный динамический метод и выполнять его.  
  
-   Динамический метод использует только открытые типы и члены. Если его набор прав включает <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, он может использовать закрытые типы и члены любой сборки, набор прав которой идентичен набору прав порождающей сборки или является его подмножеством.  
  
-   Разрешения, необходимые всем типам и членам, используемым динамическим методом, включены в набор прав сборки с частичным доверием.  
  
> [!NOTE]
>  Динамические методы не поддерживают отладочные символы.  
  
<a name="Dynamic_Methods_Associated_with_Existing_Assemblies"></a>   
## <a name="dynamic-methods-associated-with-existing-assemblies"></a>Динамические методы, связанные с существующими сборками  
 Чтобы связать динамический метод с типом или модулем в существующей сборке, используйте любой из конструкторов <xref:System.Reflection.Emit.DynamicMethod>, который указывает связанный тип или модуль. Разрешения, необходимые для вызова этих конструкторов, могут быть разными, так как при связывании динамического метода с существующим типом или модулем он получает доступ к закрытым типам и членам.  
  
-   Динамический метод, связанный с типом, имеет доступ ко всем членам этого типа, даже к закрытым, а также ко всем внутренним типам и членам в сборке, содержащей связанный тип.  
  
-   Динамический метод, связанный с модулем, имеет доступ ко всем типам и членам `internal` (`Friend` в Visual Basic, `assembly` в метаданных среды CLR) в модуле.  
  
 Кроме того, можно использовать конструктор, который задает возможность пропускать проверки видимости JIT-компилятора. Это позволяет динамическому методу получать доступ ко всем типам и членам во всех сборках независимо от уровня доступа.  
  
 Разрешения, необходимые конструктору, зависят от уровня доступа, который вы намерены предоставить динамическому методу.  
  
-   Если метод использует только открытые типы и члены и вы связываете его со своим собственным типом или модулем, никакие разрешения не требуются.  
  
-   Если вы указываете, что проверки видимости JIT-компилятора следует пропустить, конструктору требуется разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>.  
  
-   Если динамический метод связывается с другим типом, даже с типом из вашей собственной сборки, конструктору требуется разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> и разрешение <xref:System.Security.Permissions.SecurityPermission> с флагом <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=fullName>.  
  
-   Если динамический метод связывается с типом или модулем в другой сборке, конструктору требуется разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> и набор прав сборки, содержащей этот модуль. Таким образом, стек вызовов должен включать все разрешения из набора прав целевого модуля, а также разрешение <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>.  
  
    > [!NOTE]
    >  В целях обратной совместимости, если не удается удовлетворить потребность в целевом наборе прав и разрешении <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, конструктору требуется разрешение <xref:System.Security.Permissions.SecurityPermission> с флагом <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=fullName>.  
  
 Несмотря на то что элементы в этом списке описываются в терминах набора прав порождающей сборки, помните, что требования предъявляются к полному стеку вызовов, включая границы домена приложения.  
  
 Дополнительные сведения см. в описании класса <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-dynamic-methods-from-partially-trusted-code"></a>Создание динамических методов из частично доверенного кода  
  
> [!NOTE]
>  Для создания динамических методов из частично доверенного кода рекомендуется использовать [анонимно размещенные динамические методы](#Anonymously_Hosted_Dynamic_Methods).  
  
 Рассмотрим условия, в которых сборка с разрешениями на доступ к Интернету может создавать динамический метод и выполнять его.  
  
-   Либо динамический метод связан с порождающим его модулем или типом, либо его набор прав включает <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> и он связан с модулем в сборке, набор прав которой идентичен набору прав порождающей сборки или является его подмножеством.  
  
-   Динамический метод использует только открытые типы и члены. Если его набор прав включает <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> и он связан с модулем в сборке, набор прав которой идентичен набору прав порождающей сборки или является его подмножеством, он может использовать типы и члены, помеченные как `internal` (`Friend` в Visual Basic, `assembly` в метаданных среды CLR) в связанном модуле.  
  
-   Разрешения, необходимые всем типам и членам, используемым динамическим методом, включены в набор прав сборки с частичным доверием.  
  
-   Динамический метод не пропускает проверки видимости JIT-компилятора.  
  
> [!NOTE]
>  Динамические методы не поддерживают отладочные символы.  
  
<a name="Version_Information"></a>   
## <a name="version-information"></a>Сведения о версии  
 Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] политика безопасности на уровне компьютера больше не используется, и механизмом обеспечения безопасности по умолчанию становится прозрачность безопасности. См. раздел [Изменения системы безопасности](../../../docs/framework/security/security-changes.md).  
  
 Начиная с [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=fullName> больше не требуется при порождении динамических сборок и динамических методов. Этот флаг необходим во всех предыдущих версиях [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  Разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=fullName> включается по умолчанию в именованные наборы разрешений `FullTrust` и `LocalIntranet`, но не в набор разрешений `Internet`. Таким образом, в более ранних версиях [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] библиотеку с разрешениями на доступ к Интернету можно использовать только в том случае, если она выполняет метод <xref:System.Security.PermissionSet.Assert%2A> для <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Такие библиотеки требуют тщательной проверки безопасности, так как ошибки в коде могут стать причиной уязвимости. Платформа [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] позволяет создавать код в сценариях частичного доверия без предъявления каких-либо требований к безопасности, так как создание кода по сути не является привилегированной операцией. То есть созданный код имеет не больше разрешений, чем породившая его сборка. Это позволяет библиотекам, порождающим код, сохранять прозрачность для системы безопасности, что устраняет необходимость в утверждении перечисления <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit> и упрощает задачу написания безопасной библиотеки.  
  
 Кроме того, в [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] появился флаг <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> для доступа к закрытым типам и членам из частично доверенных динамических методов. В более ранних версиях [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] для динамических методов, обращающихся к закрытым типам и членам, требовался флаг <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>. Это разрешение ни в коем случае нельзя предоставлять коду с частичным доверием.  
  
 Наконец, в [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] появились анонимно размещенные методы.  
  
### <a name="obtaining-information-on-types-and-members"></a>Получение сведений о типах и членах  
 Начиная с [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] для получения сведений о закрытых типах и членах никакие разрешения не требуются. Для получения сведений, необходимых для порождения динамических методов, используется отражение. Например, объекты <xref:System.Reflection.MethodInfo> используются для порождения вызовов метода. В более ранних версиях [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] для этого требовалось разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=fullName>. Дополнительные сведения см. в разделе [Соображения о безопасности для отражения](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md).  
  
## <a name="see-also"></a>См. также  
 [Соображения о безопасности для отражения](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)   
 [Предоставление динамических методов и сборок](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)

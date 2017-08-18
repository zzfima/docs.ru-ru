---
title: "Соображения о безопасности для отражения"
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
- permissions [.NET Framework], reflection
- MethodInfo parameters
- reflection, security
- partial trust,reflection
- nonpublic members
- reflection,partial trust
- link demands
ms.assetid: 42d9dc2a-8fcc-4ff3-b002-4ff260ef3dc5
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 653b91f899da5962132577fba0df6ecfcdfde4ae
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="security-considerations-for-reflection"></a>Соображения о безопасности для отражения
Отражение дает возможность получать информацию о типах и членах, а также обращаться к членам (то есть вызывать методы и конструкторы для получения и задания значений свойств, добавления и удаления обработчиков событий и т. д.). Использование отражения для получения информации о типах и членах не ограничено. В любом коде отражение можно использовать для выполнения следующих задач:  
  
-   перечисления типов и членов и просмотра их метаданных;  
  
-   перечисления и просмотра сборок и модулей.  
  
 На использование отражения для доступа к членам, напротив, накладываются ограничения. Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], только полностью доверенный код может использовать отражение для доступа к членам, критическим с точки зрения безопасности. Кроме того, только полностью доверенный код может использовать отражение для доступа к закрытым членам, которые недоступны компилированному коду непосредственно. Наконец, код, который использует отражение для доступа к критическим с точки зрения безопасности членам, должен иметь все разрешения, требуемые этим членом, то есть ситуация такая же, как с компилированным кодом.  
  
 В зависимости от необходимых разрешений код может использовать отражение для осуществления следующих видов доступа:  
  
-   доступ к открытым членам, которые не являются критическими с точки зрения безопасности;  
  
-   доступ к закрытым членам, которые доступны скомпилированному коду, только если не являются критическими с точки зрения безопасности. Примерами подобных закрытых членов являются:  
  
    -   защищенные члены базовых классов вызывающего кода (в отражении это называется доступом на уровне семейства);  
  
    -   члены `internal` (члены `Friend` в Visual Basic) в сборке вызывающего кода (в отражении это называется доступом на уровне сборки);  
  
    -   закрытые члены других экземпляров класса, содержащего вызывающий код.  
  
 Например, для кода, выполняемого в изолированном домене приложения, доступ ограничен видами, перечисленными в этом списке, пока домену приложения не будут предоставлены дополнительные разрешения.  
  
 Начиная с [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)] при попытке доступа к членам, которые обычно недоступны, создается запрос набора прав для целевого объекта и разрешения <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>. Код, выполняемый с полным доверием (например, код в приложении, которое запускается из командной строки), может всегда удовлетворять этим разрешениям. (К нему применяются ограничения доступа к членам, критическим с точки зрения безопасности, описанные ниже в данном разделе.)  
  
 При необходимости изолированный домен приложения может предоставить разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>, как описано в разделе [Доступ к обычно недоступным членам](#accessingNormallyInaccessible) далее в этой статье.  
  
<a name="accessingSecurityCritical"></a>   
## <a name="accessing-security-critical-members"></a>Доступ к членам, критическим с точки зрения безопасности  
 Член является критическим с точки зрения безопасности, если у него есть атрибут <xref:System.Security.SecurityCriticalAttribute>, если он относится к типу с атрибутом <xref:System.Security.SecurityCriticalAttribute> или если он находится в сборке, критической с точки зрения безопасности. Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] в отношении доступа к членам, критическим с точки зрения безопасности, применяются описанные ниже правила.  
  
-   Прозрачный код не может использовать отражение для доступа к членам, критическим с точки зрения безопасности, даже если он является полностью доверенным. Создается исключение <xref:System.MethodAccessException>, <xref:System.FieldAccessException> или <xref:System.TypeAccessException>.  
  
-   Код, выполняемый с частичным доверием, рассматривается как прозрачный.  
  
 Эти правила являются одинаковыми как для прямого доступа к члену, критическому с точки зрения безопасности, из скомпилированного кода, так и для доступа с помощью отражения.  
  
 Код приложения, который запускается из командной строки, выполняется с полным доверием. Если код не помечен как прозрачный, он может использовать отражение для доступа к членам, критическим с точки зрения безопасности. При выполнении того же кода с частичным доверием (например, в изолированном домене приложения) уровень доверия сборки определяет, может ли она получить доступ к коду, критическому с точки зрения безопасности: если сборка имеет строгое имя и установлена в глобальном кэше сборок, она является доверенной и может вызывать члены, критические с точки зрения безопасности. Если код не является доверенным, он становится прозрачным даже в том случае, если не был помечен как прозрачный, и не может получить доступ к членам, критическим с точки зрения безопасности.  
  
 Дополнительные сведения о модели безопасности в [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] см. в разделе [Изменения системы безопасности](../../../docs/framework/security/security-changes.md).  
  
## <a name="reflection-and-transparency"></a>Отражение и прозрачность  
 Начиная с версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] среда CLR определяет уровень прозрачности типа или члена на основе нескольких факторов, включая уровень доверия сборки и уровень доверия домена приложения. Отражение предоставляет свойства <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Type.IsSecuritySafeCritical%2A> и <xref:System.Type.IsSecurityTransparent%2A>, которые позволяют определить уровень прозрачности типа. В таблице ниже приведены допустимые сочетания этих свойств.  
  
|Уровень безопасности|IsSecurityCritical|IsSecuritySafeCritical|IsSecurityTransparent|  
|--------------------|------------------------|----------------------------|---------------------------|  
|Critical|`true`|`false`|`false`|  
|Критический в плане безопасности|`true`|`true`|`false`|  
|Прозрачный|`false`|`false`|`true`|  
  
 Использовать эти свойства гораздо проще, чем просматривать заметки о безопасности для сборки и ее типов, проверять текущий уровень доверия и пытаться дублировать правила среды выполнения. Например, один и тот же тип может быть критическим с точки зрения безопасности при запуске из командной строки или прозрачным для системы безопасности при запуске в изолированном домене приложения.  
  
 Аналогичные свойства имеются в классах <xref:System.Reflection.MethodBase>, <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.Emit.TypeBuilder>, <xref:System.Reflection.Emit.MethodBuilder> и <xref:System.Reflection.Emit.DynamicMethod>. (Для других отражений и абстракций порождаемых отражений атрибуты безопасности применяются к связанным методам; например, в случае свойств они применяются к методам доступа к свойствам).  
  
<a name="accessingNormallyInaccessible"></a>   
## <a name="accessing-members-that-are-normally-inaccessible"></a>Доступ к обычно недоступным членам  
 Чтобы использовать отражение для вызова членов, которые недоступны в соответствии с правилами доступности среды CLR, коду необходимо предоставить одно из двух разрешений.  
  
-   Чтобы разрешить коду вызывать любой закрытый член, ему нужно предоставить разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>.  
  
    > [!NOTE]
    >  По умолчанию политика безопасности отказывает в предоставлении этого разрешения коду, полученному из Интернета. Это разрешение ни в коем случае нельзя предоставлять коду, источником которого является Интернет.  
  
-   Чтобы разрешить коду вызывать любой закрытый член, только если набор прав сборки, содержащей вызываемый член, идентичен набору прав сборки, содержащей вызывающий код, или является его подмножеством, коду необходимо предоставить разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>.  
  
 Предположим, вы предоставляете домену приложения разрешения на доступ к Интернету плюс разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, а затем запускаете веб-приложение с двумя сборками, A и B.  
  
-   Сборка A может использовать отражение для доступа к закрытым членам сборки B, так как набор прав сборки B не включает какие-либо разрешения, которые не предоставлены сборке A.  
  
-   Сборка A не может использовать отражение для доступа к закрытым членам сборок [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], таких как mscorlib.dll, так как сборка mscorlib.dll является полностью доверенной и поэтому обладает разрешениями, которые не были предоставлены сборке A. Когда управление доступом для кода обращается к стеку во время выполнения, выдается исключение <xref:System.MemberAccessException>.  
  
## <a name="serialization"></a>Сериализация  
 Что касается сериализации, разрешение <xref:System.Security.Permissions.SecurityPermission> с флагом <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A?displayProperty=fullName> предоставляет возможность получать и задавать члены сериализуемых типов независимо от доступности. Это разрешение позволяет коду обнаруживать и изменять закрытое состояние экземпляра. (Помимо наличия соответствующих разрешений тип должен быть [помечен](../../../docs/standard/attributes/applying-attributes.md) как сериализуемый в метаданных.)  
  
## <a name="parameters-of-type-methodinfo"></a>Параметры типа MethodInfo  
 Избегайте написания открытых членов, принимающих параметры <xref:System.Reflection.MethodInfo>, особенно для доверенного кода. Такие члены могут оказаться более уязвимыми для вредоносного кода. Например, рассмотрим открытый член в коде с высоким уровнем доверия, принимающий параметр <xref:System.Reflection.MethodInfo>. Предположим, что открытый член косвенно вызывает метод <xref:System.Reflection.MethodBase.Invoke%2A> для предоставленного параметра. Если открытый член не выполняет необходимые проверки разрешений, вызов метода <xref:System.Reflection.MethodBase.Invoke%2A> всегда будет успешным, так как система безопасности определяет, что вызывающий объект является полностью доверенным. Даже если вредоносный код не имеет разрешения на прямой вызов метода, он по-прежнему может сделать это косвенным образом, вызвав открытый член.  
  
## <a name="version-information"></a>Сведения о версии  
  
-   Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] прозрачный код не может использовать отражение для доступа к членам, критическим с точки зрения безопасности.  
  
-   В [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)] появился флаг <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>. В более ранних версиях [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] флаг <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> требуется для кода, который использует отражение для доступа к закрытым членам. Это разрешение, которое ни в коем случае нельзя предоставлять коду с частичным доверием.  
  
-   Начиная с версии [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] использование отражения для получения сведений о закрытых типах и членах не требует никаких разрешений. В более ранних версиях для этого требовалось разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=fullName>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Permissions.ReflectionPermissionFlag>   
 <xref:System.Security.Permissions.ReflectionPermission>   
 <xref:System.Security.Permissions.SecurityPermission>   
 [Изменения системы безопасности](../../../docs/framework/security/security-changes.md)   
 [Управление доступом для кода](../../../docs/framework/misc/code-access-security.md)   
 [Вопросы безопасности в порождении отражения](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)   
 [Просмотр сведений о типах](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Применение атрибутов](../../../docs/standard/attributes/applying-attributes.md)   
 [Доступ к пользовательским атрибутам](../../../docs/framework/reflection-and-codedom/accessing-custom-attributes.md)


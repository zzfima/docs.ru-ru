---
title: "Securing Method Access | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "code security, method access"
  - "secure coding, method access"
  - "security [.NET Framework], method access"
  - "method access security"
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Securing Method Access
Некоторые методы не подходят для вызова из произвольного ненадежного кода. С такими методами связан ряд угроз: метод может предоставить некие закрытые сведения; он может доверять всем переданным ему данным; он может не осуществлять проверку параметров; либо при передаче неверных параметров он может работать неправильно или выполнить опасную операцию. Необходимо отслеживать такие ситуации и предпринимать меры для защиты метода.  
  
 В некоторых случаях может потребоваться ограничить методы, которые не предназначены для общего использования, но по\-прежнему должны быть открытыми. Например, имеется интерфейс, который должен вызываться через собственные библиотеки DLL и поэтому должен быть открытым, но вы не хотите предоставлять к нему общий доступ, чтобы предотвратить его использование клиентами или не позволить вредоносному коду использовать точку входа в компонент. Другой распространенной причиной ограничения метода, не предназначенного для открытого использования \(но который должен быть открытым\) является задача избежать документирования и поддержки того, что является внутренним интерфейсом.  
  
> [!CAUTION]
>  Управление доступом для кода и частично доверенный код  
>   
>  Платформа .NET Framework предоставляет механизм для принудительного применения различных уровней доверия к разным частям кода, выполняемым в одном и том же приложении. Этот механизм называется управлением доступом для кода.  Управление доступом для кода в .NET Framework не следует использовать в качестве средства безопасности при работе с частично доверенным кодом, особенно кодом неизвестного происхождения. Мы не рекомендуем загружать и выполнять код из неизвестных источников, не предприняв дополнительные меры безопасности.  
>   
>  Эта политика действует в отношении всех версий платформы .NET Framework, кроме платформы .NET Framework в составе Silverlight.  
  
 Управляемый код позволяет ограничить доступ к методу несколькими способами.  
  
-   Ограничить область доступа классом, сборкой или производным классом, если они являются доверенными. Это самый простой способ ограничить доступ к методу. Обратите внимание, что обычно производные классы могут иметь более низкий уровень доверия, чем класс, от которого они наследуются, хотя в некоторых случаях они совместно используют удостоверение родительского класса. В частности, не следует определять уровень доверия по ключевому слову **protected**, которое не обязательно используется в контексте безопасности.  
  
-   Ограничить доступ к методу вызывающим объектам с определенными удостоверениями, лучше всего выбрать какое\-либо конкретное [свидетельство](http://msdn.microsoft.com/ru-ru/64ceb7c8-a0b4-46c4-97dc-6c22da0539da) \(строгое имя, издатель, зона и так далее\).  
  
-   Ограничить доступ к методу вызывающим объектам, имеющим выбранные вами разрешения.  
  
 Аналогичным образом декларативная безопасность позволяет контролировать и наследование классов. Можно использовать **InheritanceDemand**, чтобы сделать следующее.  
  
-   Потребовать, чтобы производные классы имели заданное удостоверение или разрешение.  
  
-   Потребовать, чтобы производные классы, переопределяющие некоторые методы, имели заданное удостоверение или разрешение.  
  
 В следующем примере показано, как ограничить доступ к открытому классу, требуя, чтобы вызывающие объекты были подписаны определенным строгим именем. В этом примере используется <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> с **Demand** для строгого имени. Сведения о том, как присвоить сборке строгое имя, см. в разделе [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _ Public Class Class1 End Class  
  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")] public class Class1 { }   
```  
  
## Исключение использования классов и членов ненадежным кодом  
 Используйте объявления, приведенные в этом разделе, чтобы запретить частично доверенному коду использовать определенные классы и методы, а также свойства и события. Применяя эти объявления к классу, можно применить защиту ко всем методам, свойствам и событиям. Однако, обратите внимание, что доступ к полям не зависит от декларативной безопасности. Также обратите внимание, что связывание помогает защититься от только непосредственных вызывающих объектов, и не может пресечь отвлекающие атаки.  
  
> [!NOTE]
>  Новая модель прозрачности была введена в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Модель [Security\-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) определяет безопасный код с помощью атрибута <xref:System.Security.SecurityCriticalAttribute>. Критичный в плане безопасности код требует полного доверия как к вызывающим, так и к наследующим объектам. Сборки, выполняющиеся в соответствии с правилами безопасности доступа кода из более ранних версий .NET Framework, могут вызывать сборки с уровнем 2. В этом случае критически важные для безопасности атрибуты считаются запросами связи для полного доверия.  
  
 В сборках со строгими именами [LinkDemand](../../../docs/framework/misc/link-demands.md) применяется ко всем общедоступным методам, свойствам и событиям для того, чтобы их могли использовать только полностью доверенные вызывающие объекты. Чтобы отключить эту функцию, необходимо применить атрибут <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Таким образом, явное выделение классов для исключения ненадежных вызывающих объектов необходимо только для сборки без подписи или с этим атрибутом; эти объявления можно использовать для пометки подмножества типов, которые не предназначены для ненадежных вызывающих объектов.  
  
 В следующих примерах показано, как осуществить запрет использования классов и членов ненадежным кодом.  
  
 Для открытых незапечатанных классов:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _ System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ Public Class CanDeriveFromMe End Class  
  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public class CanDeriveFromMe { }  
```  
  
 Для открытых запечатанных классов:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ NotInheritable Public Class CannotDeriveFromMe End Class  
  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public sealed class CannotDeriveFromMe { }  
```  
  
 Для открытых абстрактных классов:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _ System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _ MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public abstract class CannotCreateInstanceOfMe_CanCastToMe{}  
```  
  
 Для открытых виртуальных функций:  
  
```vb  
Class Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Overridable Sub CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Base1  
```  
  
```csharp  
class Base1 { [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")] [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public virtual void CanOverrideOrCallMe() {} }  
```  
  
 Для открытых абстрактных функций:  
  
```vb  
MustInherit Class Base2 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Sub MustOverrideMe() End Sub End Class 'Base2  
```  
  
```csharp  
abstract class Base2{ [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute( System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] public abstract void MustOverrideMe(); }  
```  
  
 Для открытых переопределяемых функций в случае, когда базовый класс не требует полного доверия:  
  
```vb  
Class Derived Inherits Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _ Public Overrides Sub CanOverrideOrCallMe() MyBase.CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Derived  
```  
  
```csharp  
class Derived : Base1 { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")] public override void CanOverrideOrCallMe() { base.CanOverrideOrCallMe(); } }  
```  
  
 Для открытых переопределяемых функций в случае, когда базовый класс требует полного доверия:  
  
```vb  
Class Derived Inherits Base1 <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _ Public Overrides Sub CanOverrideOrCallMe() MyBase.CanOverrideOrCallMe() End Sub 'CanOverrideOrCallMe End Class 'Derived  
```  
  
```csharp  
class Derived : Base1 { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")] public override void CanOverrideOrCallMe() { base.CanOverrideOrCallMe(); } }  
```  
  
 Для открытых интерфейсов:  
  
```vb  
Public Interface ICanCastToMe <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _ Sub CanImplementMe() End Interface 'ICanCastToMe <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _ Class Implemented Implements ICanCastToMe Public Sub CanImplementMe() End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe { [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] void CanImplementMe(); } [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")] [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")] class Implemented : ICanCastToMe { public void CanImplementMe() { } }  
```  
  
## Переопределение объявлений Virtual и Internal или Overloads Overridable Friend  
  
> [!NOTE]
>  В этом разделе рассматривается проблема безопасности при объявлении метода как `virtual` и `internal` \(`Overloads``Overridable``Friend` в Visual Basic\). Это предупреждение относится только к версии .NET Framework 1.0 и 1.1, оно не применяется к версии 2.0.  
  
 В платформе .NET Framework версий 1.0 и 1.1 необходимо учитывать особенности организации доступа в системе типов, когда код делается недоступным для других сборок. Метод, объявленный **virtual** \(виртуальным\) и **internal** \(внутренним\) \(**Overloads Overridable Friend** в Visual Basic\), может переопределить запись vtable родительского класса и может использоваться только в пределах той же сборки, так как он является внутренним. Однако доступность метода для переопределения напрямую определяется ключевым словом **virtual** и его можно переопределить из другой сборки, при условии, что ее код имеет доступ к самому классу. Если такая возможность переопределения представляет собой проблему, используйте для исправления  декларативную безопасность, либо удалите ключевое слово **virtual**, если в нем нет необходимости.  
  
 Обратите внимание, что даже если компилятор предотвращает такие переопределения, выдавая ошибку компиляции, все равно возможно, что код будет скомпилирован с другими компиляторами для переопределения.  
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)
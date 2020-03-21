---
title: Безопасность доступа к методам
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
ms.openlocfilehash: a9e1226483eaa02dc8dc3dfb741e3df6b2985fbe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181155"
---
# <a name="securing-method-access"></a><span data-ttu-id="d76a6-102">Безопасность доступа к методам</span><span class="sxs-lookup"><span data-stu-id="d76a6-102">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="d76a6-103">Некоторые методы не подходят для вызова из произвольного ненадежного кода.</span><span class="sxs-lookup"><span data-stu-id="d76a6-103">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="d76a6-104">С такими методами связан ряд угроз: метод может предоставить некие закрытые сведения; он может доверять всем переданным ему данным; он может не осуществлять проверку параметров; либо при передаче неверных параметров он может работать неправильно или выполнить опасную операцию.</span><span class="sxs-lookup"><span data-stu-id="d76a6-104">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="d76a6-105">Необходимо отслеживать такие ситуации и предпринимать меры для защиты метода.</span><span class="sxs-lookup"><span data-stu-id="d76a6-105">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="d76a6-106">В некоторых случаях может потребоваться ограничить методы, которые не предназначены для общего использования, но по-прежнему должны быть открытыми.</span><span class="sxs-lookup"><span data-stu-id="d76a6-106">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="d76a6-107">Например, имеется интерфейс, который должен вызываться через собственные библиотеки DLL и поэтому должен быть открытым, но вы не хотите предоставлять к нему общий доступ, чтобы предотвратить его использование клиентами или не позволить вредоносному коду использовать точку входа в компонент.</span><span class="sxs-lookup"><span data-stu-id="d76a6-107">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="d76a6-108">Другой распространенной причиной ограничения метода, не предназначенного для открытого использования (но который должен быть открытым) является задача избежать документирования и поддержки того, что является внутренним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="d76a6-108">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be a very internal interface.</span></span>  
  
 <span data-ttu-id="d76a6-109">Управляемый код позволяет ограничить доступ к методу несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="d76a6-109">Managed code offers several ways to restrict method access:</span></span>  
  
- <span data-ttu-id="d76a6-110">Ограничить область доступа классом, сборкой или производным классом, если они являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="d76a6-110">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="d76a6-111">Это самый простой способ ограничить доступ к методу.</span><span class="sxs-lookup"><span data-stu-id="d76a6-111">This is the simplest way to limit method access.</span></span> <span data-ttu-id="d76a6-112">Обратите внимание, что обычно производные классы могут иметь более низкий уровень доверия, чем класс, от которого они наследуются, хотя в некоторых случаях они совместно используют удостоверение родительского класса.</span><span class="sxs-lookup"><span data-stu-id="d76a6-112">Note that, in general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="d76a6-113">В частности, не следует делать вывод о доверии из **защищенного**ключевого слова, которое не обязательно используется в контексте безопасности.</span><span class="sxs-lookup"><span data-stu-id="d76a6-113">In particular, do not infer trust from the keyword **protected**, which is not necessarily used in the security context.</span></span>  
  
- <span data-ttu-id="d76a6-114">Ограничьте доступ к методу для абонентов указанной идентификации - по сути, любые конкретные [доказательства](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (сильное имя, издатель, зона, и так далее) вы выбираете.</span><span class="sxs-lookup"><span data-stu-id="d76a6-114">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
- <span data-ttu-id="d76a6-115">Ограничить доступ к методу вызывающим объектам, имеющим выбранные вами разрешения.</span><span class="sxs-lookup"><span data-stu-id="d76a6-115">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="d76a6-116">Аналогичным образом декларативная безопасность позволяет контролировать и наследование классов.</span><span class="sxs-lookup"><span data-stu-id="d76a6-116">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="d76a6-117">Вы можете использовать **InheritanceDemand** для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d76a6-117">You can use **InheritanceDemand** to do the following:</span></span>  
  
- <span data-ttu-id="d76a6-118">Потребовать, чтобы производные классы имели заданное удостоверение или разрешение.</span><span class="sxs-lookup"><span data-stu-id="d76a6-118">Require derived classes to have a specified identity or permission.</span></span>  
  
- <span data-ttu-id="d76a6-119">Потребовать, чтобы производные классы, переопределяющие некоторые методы, имели заданное удостоверение или разрешение.</span><span class="sxs-lookup"><span data-stu-id="d76a6-119">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="d76a6-120">В следующем примере показано, как ограничить доступ к открытому классу, требуя, чтобы вызывающие объекты были подписаны определенным строгим именем.</span><span class="sxs-lookup"><span data-stu-id="d76a6-120">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="d76a6-121">В этом <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> примере используется **требование к** сильному имени.</span><span class="sxs-lookup"><span data-stu-id="d76a6-121">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="d76a6-122">Для информации о том, как подписать сборку с сильным именем, [см.](../../standard/assembly/create-use-strong-named.md)</span><span class="sxs-lookup"><span data-stu-id="d76a6-122">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../standard/assembly/create-use-strong-named.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="d76a6-123">Исключение использования классов и членов ненадежным кодом</span><span class="sxs-lookup"><span data-stu-id="d76a6-123">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="d76a6-124">Используйте объявления, приведенные в этом разделе, чтобы запретить частично доверенному коду использовать определенные классы и методы, а также свойства и события.</span><span class="sxs-lookup"><span data-stu-id="d76a6-124">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="d76a6-125">Применяя эти объявления к классу, можно применить защиту ко всем методам, свойствам и событиям. Однако, обратите внимание, что доступ к полям не зависит от декларативной безопасности.</span><span class="sxs-lookup"><span data-stu-id="d76a6-125">By applying these declarations to a class, you apply the protection to all its methods, properties, and events; however, note that field access is not affected by declarative security.</span></span> <span data-ttu-id="d76a6-126">Также обратите внимание, что связывание помогает защититься от только непосредственных вызывающих объектов, и не может пресечь отвлекающие атаки.</span><span class="sxs-lookup"><span data-stu-id="d76a6-126">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d76a6-127">Новая модель прозрачности была введена в рамках .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d76a6-127">A new transparency model has been introduced in the .NET Framework 4.</span></span> <span data-ttu-id="d76a6-128">Код [security-Transparent Code,](security-transparent-code-level-2.md) модель уровня 2 <xref:System.Security.SecurityCriticalAttribute> идентифицирует безопасный код с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="d76a6-128">The [Security-Transparent Code, Level 2](security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="d76a6-129">Критичный в плане безопасности код требует полного доверия как к вызывающим, так и к наследующим объектам.</span><span class="sxs-lookup"><span data-stu-id="d76a6-129">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="d76a6-130">Сборки, выполняющиеся в соответствии с правилами безопасности доступа кода из более ранних версий .NET Framework, могут вызывать сборки с уровнем 2.</span><span class="sxs-lookup"><span data-stu-id="d76a6-130">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="d76a6-131">В этом случае критически важные для безопасности атрибуты считаются запросами связи для полного доверия.</span><span class="sxs-lookup"><span data-stu-id="d76a6-131">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="d76a6-132">В сильных иных собраниях [LinkDemand](link-demands.md) применяется ко всем общедоступным методам, свойствам и событиям, которые в них могут ограничить их использование полностью доверенным абонентом.</span><span class="sxs-lookup"><span data-stu-id="d76a6-132">In strong-named assemblies, a [LinkDemand](link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="d76a6-133">Чтобы отключить эту возможность, необходимо применить атрибут <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d76a6-133">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="d76a6-134">Таким образом, явное выделение классов для исключения ненадежных вызывающих объектов необходимо только для сборки без подписи или с этим атрибутом; эти объявления можно использовать для пометки подмножества типов, которые не предназначены для ненадежных вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="d76a6-134">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="d76a6-135">В следующих примерах показано, как осуществить запрет использования классов и членов ненадежным кодом.</span><span class="sxs-lookup"><span data-stu-id="d76a6-135">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="d76a6-136">Для открытых незапечатанных классов:</span><span class="sxs-lookup"><span data-stu-id="d76a6-136">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="d76a6-137">Для открытых запечатанных классов:</span><span class="sxs-lookup"><span data-stu-id="d76a6-137">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="d76a6-138">Для открытых абстрактных классов:</span><span class="sxs-lookup"><span data-stu-id="d76a6-138">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="d76a6-139">Для открытых виртуальных функций:</span><span class="sxs-lookup"><span data-stu-id="d76a6-139">For public virtual functions:</span></span>  
  
```vb  
Class Base1
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="d76a6-140">Для открытых абстрактных функций:</span><span class="sxs-lookup"><span data-stu-id="d76a6-140">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="d76a6-141">Для открытых переопределяемых функций в случае, когда базовый класс не требует полного доверия:</span><span class="sxs-lookup"><span data-stu-id="d76a6-141">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="d76a6-142">Для открытых переопределяемых функций в случае, когда базовый класс требует полного доверия:</span><span class="sxs-lookup"><span data-stu-id="d76a6-142">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="d76a6-143">Для открытых интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="d76a6-143">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="d76a6-144">Переопределение объявлений Virtual и Internal или Overloads Overridable Friend</span><span class="sxs-lookup"><span data-stu-id="d76a6-144">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d76a6-145">Этот раздел предупреждает о проблеме безопасности `virtual` `internal` при`Overloads` `Overridable` `Friend` объявлении метода как и (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d76a6-145">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="d76a6-146">Это предупреждение распространяется только на версии .NET Framework 1.0 и 1.1, оно не распространяется на более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="d76a6-146">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="d76a6-147">В версиях .NET Framework 1.0 и 1.1 вы должны быть осведомлены о нюансах доступности системы типа, подтверждая, что ваш код недоступен для других сборок.</span><span class="sxs-lookup"><span data-stu-id="d76a6-147">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="d76a6-148">Метод, объявленный **виртуальным** и **внутренним** **(Перегрузки Перезагрузки Overridable Friend** в Visual Basic) может переопределить вход в vtable родительского класса и может использоваться только из одной и той же сборки, поскольку он является внутренним.</span><span class="sxs-lookup"><span data-stu-id="d76a6-148">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="d76a6-149">Однако доступность для переопределения определяется **виртуальным** ключевым словом, и это может быть отменено из другой сборки до тех пор, пока этот код имеет доступ к самому классу.</span><span class="sxs-lookup"><span data-stu-id="d76a6-149">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="d76a6-150">Если возможность переопределения представляет собой проблему, используйте декларативную безопасность, чтобы исправить ее, или удалите **виртуальное** ключевое слово, если оно не требуется строго.</span><span class="sxs-lookup"><span data-stu-id="d76a6-150">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="d76a6-151">Обратите внимание, что даже если компилятор предотвращает такие переопределения, выдавая ошибку компиляции, все равно возможно, что код будет скомпилирован с другими компиляторами для переопределения.</span><span class="sxs-lookup"><span data-stu-id="d76a6-151">Note that even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76a6-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d76a6-152">See also</span></span>

- [<span data-ttu-id="d76a6-153">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="d76a6-153">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)

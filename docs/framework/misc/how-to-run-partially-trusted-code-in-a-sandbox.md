---
title: Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: b2f5a72e747f6c71743a7b22fe9f1962ac2f6b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181180"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a>Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Изолирование в песочнице — это способ запуска кода в ограниченной среде безопасности, ограничивающей разрешения доступа, предоставленные коду. Например, если имеется управляемая библиотека, полученная из источника с неполным доверием, не следует запускать ее как полностью доверенную. Вместо этого следует поместить код в "песочницу", которая ограничивает разрешения кода, которые необходимы ему по вашему мнению (например, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).  
  
 Изолирование в песочнице также можно использовать для тестирования кода, который будет распространяться для запуска в частично доверенных средах.  
  
 Использование объекта <xref:System.AppDomain> — это эффективный способ предоставления песочницы для управляемых приложений. Домены приложений, используемые для запуска частично доверенного кода, имеют разрешения, которые определяют защищенные ресурсы, доступные при запуске в этом домене <xref:System.AppDomain>. Код, выполняемый в домене <xref:System.AppDomain>, ограничивается разрешениями для домена <xref:System.AppDomain> и может осуществлять доступ только к заданным ресурсам. Домен <xref:System.AppDomain> также включает массив <xref:System.Security.Policy.StrongName>, используемый для определения сборок, которые необходимо загрузить как полностью доверенные. Это позволяет создателю домена <xref:System.AppDomain> запустить новый домен в песочнице, который разрешает выполнение определенных вспомогательных сборок с полным доверием. Чтобы загрузить сборки в качестве полностью доверенных, можно также разместить их в глобальном кэше сборок. Однако в этом случае они загрузятся как полностью доверенные во всех доменах приложений, созданных на компьютере. Список строгих имен позволяет принимать решение по каждому домену <xref:System.AppDomain>, что обеспечивает более точное определение.  
  
 Чтобы задать набор разрешений для приложений, выполняемых в песочнице, можно использовать перегрузку метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>. Она позволяет точно установить требуемый уровень управления доступом для кода. Сборки, загружаемые в <xref:System.AppDomain> с помощью этой перегрузки, могут иметь заданный набор прав или являться полностью доверенными. Сборке предоставляется полное доверие, если она находится в глобальном кэше сборок или указана в параметре массива `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>). В список `fullTrustAssemblies` следует добавлять только сборки, о которых известно, что они являются полностью доверенными.  
  
 Перегрузка имеет следующую подпись:  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 Параметры перегрузки метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> задают имя домена <xref:System.AppDomain>, свидетельство для домена <xref:System.AppDomain>, объект <xref:System.AppDomainSetup>, определяющий базовую папку приложения для песочницы, используемый набор разрешений и строгие имена для полностью доверенных сборок.  
  
 По соображениям безопасности базовая папка приложения, указанная в параметре `info`, не должна совпадать с базовой папкой ведущего приложения.  
  
 В качестве значения параметра `grantSet` можно задать либо явным образом созданный набор разрешений, либо стандартный набор разрешений, созданный методом <xref:System.Security.SecurityManager.GetStandardSandbox%2A>.  
  
 В отличие от большинства перегрузок <xref:System.AppDomain>, свидетельство для домена <xref:System.AppDomain> (предоставляемое параметром `securityInfo`) не используется для определения набора прав, предоставленного частично доверенным сборкам. Этот набор определяется независимо с помощью параметра `grantSet`. Однако свидетельство можно использовать в иных целях, например для определения области изолированного хранилища.  
  
### <a name="to-run-an-application-in-a-sandbox"></a>Запуск приложения в песочнице  
  
1. Создайте набор разрешений, которые нужно предоставить ненадежному приложению. Минимальное разрешение, которое можно предоставить, — <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>. Кроме того, можно предоставить дополнительные разрешения, которые, по вашему мнению, будут безопасными для ненадежного кода, например разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission>. Во фрагменте кода ниже показано создание набора разрешений, в котором содержится только одно разрешение <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     Также можно использовать существующий именованный набор разрешений, например Internet.  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     Метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A> возвращает набор разрешений `Internet` или `LocalIntranet` в зависимости от зоны в свидетельстве. Метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A> также создает разрешения идентификации для некоторых объектов свидетельства, переданных по ссылке.  
  
2. Подпишите сборку, которая содержит размещающий класс (в этом примере это класс `Sandboxer`), вызывающий ненадежный код. Добавьте объект <xref:System.Security.Policy.StrongName>, используемый для подписания сборки, в массив <xref:System.Security.Policy.StrongName> в параметре `fullTrustAssemblies` вызова метода <xref:System.AppDomain.CreateDomain%2A>. Чтобы разрешить выполнение кода с частичным доверием или предложить службы приложению с частичным доверием, нужно запустить размещающий класс как полностью доверенный. Ниже показано, как читается строгое имя <xref:System.Security.Policy.StrongName> сборки.  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     Сборки .NET Framework, такие как mscorlib и System.dll, не обязательно добавлять в список полностью доверенных сборок, так как они загружаются как полностью доверенные из глобального кэша сборок.  
  
3. Инициализируйте параметр <xref:System.AppDomainSetup> метода <xref:System.AppDomain.CreateDomain%2A>. С помощью этого параметра можно управлять многими настройками нового домена <xref:System.AppDomain>. Свойство <xref:System.AppDomainSetup.ApplicationBase%2A> является важной настройкой и должно отличаться от свойства <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain> основного приложения. Если значения <xref:System.AppDomainSetup.ApplicationBase%2A> совпадают, частично доверенное приложение может заставить ведущее приложение загрузить (как полностью доверенное) определяемое им исключение, тем самым создав угрозу безопасности. Это еще одна причина, по которой не рекомендуется выполнять перехват исключения. Чтобы снизить риск злоумышленного использования, необходимо задать для основного и изолированного приложений разные базовые папки.  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. Чтобы создать домен приложения с использованием заданных параметров, вызовите перегрузку метода <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>.  
  
     Подпись этого метода следующая:  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     Дополнительные сведения:  
  
    - Это единственная перегрузка метода <xref:System.AppDomain.CreateDomain%2A>, принимающая в качестве параметра набор разрешений <xref:System.Security.PermissionSet>, то есть единственная перегрузка, позволяющая загружать приложение в режиме частичного доверия.  
  
    - Параметр `evidence` не используется для вычисления набора разрешений. Он служит для идентификации другими компонентами .NET Framework.  
  
    - Задание свойства <xref:System.AppDomainSetup.ApplicationBase%2A> параметра `info` является обязательным для этой перегрузки.  
  
    - Параметр `fullTrustAssemblies` имеет ключевое слово `params`, означающее, что создавать массив <xref:System.Security.Policy.StrongName> не обязательно. Разрешается передавать в качестве параметров ноль, одно или несколько строгих имен.  
  
    - Для создания домена приложения используйте следующий код:  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. Загрузите код в созданный ранее изолирующий домен <xref:System.AppDomain>. Это можно сделать двумя способами:  
  
    - Вызовите для сборки метод <xref:System.AppDomain.ExecuteAssembly%2A>.  
  
    - Используйте метод <xref:System.Activator.CreateInstanceFrom%2A> для создания экземпляра класса, производного от <xref:System.MarshalByRefObject>, в новом домене <xref:System.AppDomain>.  
  
     Предпочтительнее использовать второй метод, так как в этом случае легче передавать параметры новому экземпляру домена <xref:System.AppDomain>. Метод <xref:System.Activator.CreateInstanceFrom%2A> предоставляет две важные возможности.  
  
    - Во-первых, можно использовать базу кода, указывающую на расположение, которое не содержит вашу сборку.  
  
    - Во-вторых, при работе в режиме полного доверия (<xref:System.Security.CodeAccessPermission.Assert%2A>) можно использовать для создания экземпляра критически важного класса метод <xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>. (Это происходит всякий раз, когда ваша сборка не имеет маркировки прозрачности и загружается как полностью доверенные.) Поэтому вы должны быть осторожны, чтобы создать только код, который вы доверяете с этой функцией, и мы рекомендуем создавать только экземпляры полностью доверенных классов в новом домене приложения.  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     Обратите внимание, что для создания экземпляра класса в новом домене класс должен расширять класс <xref:System.MarshalByRefObject>.  
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. Распакуйте новый экземпляр домена в ссылку в этом домене. Эта ссылка используется для выполнения ненадежного кода.  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. Вызовите метод `ExecuteUntrustedCode` в созданном экземпляре класса `Sandboxer`.  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     Этот вызов выполняется в изолированном домене приложения, который имеет ограниченные разрешения.  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <xref:System.Reflection> используется для получения дескриптора метода в сборке с частичным доверием. Этот дескриптор можно использовать для безопасного выполнения кода с минимальными разрешениями.  
  
     В предыдущем коде обратите внимание на метод <xref:System.Security.PermissionSet.Assert%2A> для получения разрешения с полным доверием перед печатью <xref:System.Security.SecurityException>.  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     Утверждение с полным доверием используется для получения расширенной информации из <xref:System.Security.SecurityException>. Если не используется утверждение <xref:System.Security.PermissionSet.Assert%2A>, метод <xref:System.Security.SecurityException.ToString%2A> исключения <xref:System.Security.SecurityException> обнаружит наличие в стеке кода с частичным доверием и ограничит возвращенные сведения. Если бы код с частичным доверием мог считать эти сведения, создалась бы угроза безопасности. Во избежание этого разрешение <xref:System.Security.Permissions.UIPermission> не предоставляется. Утверждения полного доверия нужно использовать очень осторожно и только в том случае, если вы уверены, что уровень разрешений кода с частичным доверием не повысится до уровня полного доверия. Как правило, не следует вызывать код без полного доверия в той же функции и после вызова утверждения полного доверия. Рекомендуется всегда отменять утверждение после завершения его использования.  
  
## <a name="example"></a>Пример  
 В примере ниже реализуется процедура, описанная в предыдущем подразделе. В этом примере проект с именем `Sandboxer` в решении Visual Studio содержит проект с именем `UntrustedCode`, реализующий класс `UntrustedClass`. В этом сценарии предполагается, что загружена библиотечная сборка, содержащая метод, который должен вернуть значение `true` или `false`, указывающее, является ли предоставленное число числом Фибоначчи. Вместо этого метод пытается считать файл с компьютера. В примере кода ниже показан ненадежный код.  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 В примере ниже показан код приложения `Sandboxer`, выполняющий ненадежный код.  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Правила написания безопасного кода](../../standard/security/secure-coding-guidelines.md)

---
title: Внутрипроцессное параллельное выполнение
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 5ca2f03576946a23b3133bbe7532d46c4ad758ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181667"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="b0d0e-102">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="b0d0e-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="b0d0e-103">Начиная с .NET Framework 4, разработчики могут использовать внутрипроцессное параллельное размещение для запуска нескольких версий среды CLR в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-103">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="b0d0e-104">Управляемые COM-компоненты по умолчанию выполняются в той версии платформы .NET Framework, в которой они были созданы, вне зависимости от загруженной для процесса версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="b0d0e-105">Фон</span><span class="sxs-lookup"><span data-stu-id="b0d0e-105">Background</span></span>  
 <span data-ttu-id="b0d0e-106">Платформа .NET Framework всегда предоставляла возможность параллельного размещения для приложений с управляемым кодом, но до появления версии .NET Framework 4 эта функция не была доступна для управляемых COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="b0d0e-107">Загруженные в процесс COM-компоненты в прошлом выполнялись в уже загруженной версии среды выполнения или в последней установленной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="b0d0e-108">Если эта версия была несовместима с COM-компонентом, то выполнение завершалось ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="b0d0e-109">Платформа .NET Framework 4 предоставляет новый подход к параллельному размещению, который обеспечивает выполнение следующих требований:</span><span class="sxs-lookup"><span data-stu-id="b0d0e-109">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="b0d0e-110">Установка новой версии платформы .NET Framework не повлияет на существующие приложения.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="b0d0e-111">Приложения будут выполняться в той версии платформы .NET Framework, в которой они были построены.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="b0d0e-112">Новая версия платформы .NET Framework не используется, если явным образом не указано иное.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="b0d0e-113">В то же время приложения легче перевести на использование новой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="b0d0e-114">Влияние на пользователей и разработчиков</span><span class="sxs-lookup"><span data-stu-id="b0d0e-114">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="b0d0e-115">**Конечные пользователи и системные администраторы**.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-115">**End users and system administrators**.</span></span> <span data-ttu-id="b0d0e-116">Эти группы пользователей теперь могут быть уверены, что установка новой версии среды выполнения (отдельно или вместе с приложением) не окажет влияния на работу компьютера.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="b0d0e-117">Существующие приложения будут выполняться, как раньше.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-117">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="b0d0e-118">**Разработчики приложений**.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-118">**Application developers**.</span></span> <span data-ttu-id="b0d0e-119">Параллельное размещение не затрагивает разработчиков приложений.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="b0d0e-120">Приложения по умолчанию всегда выполняются в версиях платформы .NET Framework, в которых они были созданы. Это поведение не изменено.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="b0d0e-121">Разработчики могут переопределить это поведение и настроить приложение на выполнение в более новой версии платформы .NET Framework (см. [сценарий 2](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="b0d0e-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="b0d0e-122">**Разработчики и пользователи библиотек**.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-122">**Library developers and consumers**.</span></span> <span data-ttu-id="b0d0e-123">Параллельное размещение не устраняет проблемы совместимости, с которыми сталкиваются разработчики библиотек.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="b0d0e-124">Библиотека, загруженная приложением напрямую (через прямую ссылку или с помощью вызова <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>) продолжает использовать среду выполнения класса <xref:System.AppDomain>, в который она загружена.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="b0d0e-125">Следует проверить корректность работы библиотек со всеми версиями платформы .NET Framework, поддержка которых необходима.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="b0d0e-126">Если приложение компилируется с помощью среды выполнения .NET Framework 4, но содержит библиотеку, построенную с помощью более старой среды выполнения, эта библиотека также будет использовать среду выполнения .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-126">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="b0d0e-127">Но, если приложение было создано с помощью более старой среды выполнения и библиотеки, которая построена в .NET Framework 4, приложение также необходимо явным образом настроить на использование .NET Framework 4 (см. [сценарий 3](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="b0d0e-127">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="b0d0e-128">**Разработчики управляемых COM-компонентов**.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-128">**Managed COM component developers**.</span></span> <span data-ttu-id="b0d0e-129">Управляемые COM-компоненты ранее автоматически выполнялись в последней версии среды выполнения, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="b0d0e-130">Теперь COM-компоненты можно запускать в той версии среды выполнения, в которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="b0d0e-131">Как отражено в следующей таблице, созданные на платформе .NET Framework версии 1.1 компоненты могут запускаться параллельно с компонентами версии 4, но не могут выполняться вместе с компонентами версий 2.0, 3.0 или 3.5, так как параллельное размещение для этих версий невозможно.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="b0d0e-132">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b0d0e-132">.NET Framework version</span></span>|<span data-ttu-id="b0d0e-133">1.1</span><span class="sxs-lookup"><span data-stu-id="b0d0e-133">1.1</span></span>|<span data-ttu-id="b0d0e-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="b0d0e-134">2.0 - 3.5</span></span>|<span data-ttu-id="b0d0e-135">4</span><span class="sxs-lookup"><span data-stu-id="b0d0e-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="b0d0e-136">1.1</span><span class="sxs-lookup"><span data-stu-id="b0d0e-136">1.1</span></span>|<span data-ttu-id="b0d0e-137">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="b0d0e-137">Not applicable</span></span>|<span data-ttu-id="b0d0e-138">Нет</span><span class="sxs-lookup"><span data-stu-id="b0d0e-138">No</span></span>|<span data-ttu-id="b0d0e-139">Да</span><span class="sxs-lookup"><span data-stu-id="b0d0e-139">Yes</span></span>|  
    |<span data-ttu-id="b0d0e-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="b0d0e-140">2.0 - 3.5</span></span>|<span data-ttu-id="b0d0e-141">Нет</span><span class="sxs-lookup"><span data-stu-id="b0d0e-141">No</span></span>|<span data-ttu-id="b0d0e-142">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="b0d0e-142">Not applicable</span></span>|<span data-ttu-id="b0d0e-143">Да</span><span class="sxs-lookup"><span data-stu-id="b0d0e-143">Yes</span></span>|  
    |<span data-ttu-id="b0d0e-144">4</span><span class="sxs-lookup"><span data-stu-id="b0d0e-144">4</span></span>|<span data-ttu-id="b0d0e-145">Да</span><span class="sxs-lookup"><span data-stu-id="b0d0e-145">Yes</span></span>|<span data-ttu-id="b0d0e-146">Да</span><span class="sxs-lookup"><span data-stu-id="b0d0e-146">Yes</span></span>|<span data-ttu-id="b0d0e-147">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="b0d0e-147">Not applicable</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b0d0e-148">Версии платформы .NET Framework 3.0 и 3.5 созданы с помощью инкрементального построения на базе версии 2.0 и не требуют параллельного запуска.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="b0d0e-149">По сути они представляют собой одну и ту же версию.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="b0d0e-150">Общие сценарии параллельного размещения</span><span class="sxs-lookup"><span data-stu-id="b0d0e-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="b0d0e-151">**Сценарий 1.** Собственное приложение, которое использует COM-компоненты, созданные в более ранних версиях платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="b0d0e-152">Установленные версии платформы .NET Framework. .NET Framework 4 и все остальные версии платформы .NET Framework, используемые COM-компонентами.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-152">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="b0d0e-153">Необходимые действия: в этой ситуации не следует предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="b0d0e-154">COM-компоненты будут выполняться в той версии платформы .NET Framework, в которой они были зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="b0d0e-155">**Сценарий 2**. Управляемое приложение, созданное в .NET Framework 2.0 с пакетом обновления 1 (SP1), можно запустить .NET Framework 4, если версия 2 отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-155">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the .NET Framework 2.0, but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="b0d0e-156">Установленные версии платформы .NET Framework. Более ранняя версия .NET Framework и .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-156">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b0d0e-157">Необходимые действия: откройте [файл конфигурации приложения](../configure-apps/index.md) в каталоге приложения и используйте [элемент \<startup>](../configure-apps/file-schema/startup/startup-element.md) и [элемент \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b0d0e-157">What to do: In the [application configuration file](../configure-apps/index.md) in the application directory, use the [\<startup> element](../configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="b0d0e-158">**Сценарий 3.** Собственное приложение, которое использует COM-компоненты, созданные в более ранних версиях платформы .NET Framework. При этом приложение необходимо запустить в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b0d0e-159">Установленные версии платформы .NET Framework. .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-159">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b0d0e-160">Необходимые действия: откройте файл конфигурации приложения в каталоге приложения и используйте элемент `<startup>`, атрибут `useLegacyV2RuntimeActivationPolicy` которого имеет значение `true`, и набор элементов `<supportedRuntime>` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b0d0e-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="b0d0e-161">Пример</span><span class="sxs-lookup"><span data-stu-id="b0d0e-161">Example</span></span>  
 <span data-ttu-id="b0d0e-162">В следующем примере показан неуправляемый узел COM, в котором управляемый COM-компонент выполняется с помощью версии платформы .NET Framework, для которой был предназначен данный компонент.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="b0d0e-163">Для выполнения следующего примера скомпилируйте и зарегистрируйте следующий управляемый компонент COM с помощью .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-163">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="b0d0e-164">Чтобы зарегистрировать компонент, в меню **Проект** выберите пункт **Свойства**, перейдите на вкладку **Сборка**, а затем установите флажок **Регистрация для COM-взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b0d0e-165">Скомпилируйте следующее неуправляемое приложение C++, которое активирует COM-объект, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b0d0e-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0d0e-166">См. также</span><span class="sxs-lookup"><span data-stu-id="b0d0e-166">See also</span></span>

- [<span data-ttu-id="b0d0e-167">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="b0d0e-167">\<startup> Element</span></span>](../configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="b0d0e-168">\<Поддерживаемый элемент среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b0d0e-168">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)

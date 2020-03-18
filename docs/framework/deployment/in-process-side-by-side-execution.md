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
# <a name="in-process-side-by-side-execution"></a>Внутрипроцессное параллельное выполнение
Начиная с .NET Framework 4, разработчики могут использовать внутрипроцессное параллельное размещение для запуска нескольких версий среды CLR в одном процессе. Управляемые COM-компоненты по умолчанию выполняются в той версии платформы .NET Framework, в которой они были созданы, вне зависимости от загруженной для процесса версии .NET Framework.  
  
## <a name="background"></a>Фон  
 Платформа .NET Framework всегда предоставляла возможность параллельного размещения для приложений с управляемым кодом, но до появления версии .NET Framework 4 эта функция не была доступна для управляемых COM-компонентов. Загруженные в процесс COM-компоненты в прошлом выполнялись в уже загруженной версии среды выполнения или в последней установленной версии платформы .NET Framework. Если эта версия была несовместима с COM-компонентом, то выполнение завершалось ошибкой.  
  
 Платформа .NET Framework 4 предоставляет новый подход к параллельному размещению, который обеспечивает выполнение следующих требований:  
  
- Установка новой версии платформы .NET Framework не повлияет на существующие приложения.  
  
- Приложения будут выполняться в той версии платформы .NET Framework, в которой они были построены. Новая версия платформы .NET Framework не используется, если явным образом не указано иное. В то же время приложения легче перевести на использование новой версии платформы .NET Framework.  
  
## <a name="effects-on-users-and-developers"></a>Влияние на пользователей и разработчиков  
  
- **Конечные пользователи и системные администраторы**. Эти группы пользователей теперь могут быть уверены, что установка новой версии среды выполнения (отдельно или вместе с приложением) не окажет влияния на работу компьютера. Существующие приложения будут выполняться, как раньше.  
  
- **Разработчики приложений**. Параллельное размещение не затрагивает разработчиков приложений. Приложения по умолчанию всегда выполняются в версиях платформы .NET Framework, в которых они были созданы. Это поведение не изменено. Разработчики могут переопределить это поведение и настроить приложение на выполнение в более новой версии платформы .NET Framework (см. [сценарий 2](#scenarios)).  
  
- **Разработчики и пользователи библиотек**. Параллельное размещение не устраняет проблемы совместимости, с которыми сталкиваются разработчики библиотек. Библиотека, загруженная приложением напрямую (через прямую ссылку или с помощью вызова <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>) продолжает использовать среду выполнения класса <xref:System.AppDomain>, в который она загружена. Следует проверить корректность работы библиотек со всеми версиями платформы .NET Framework, поддержка которых необходима. Если приложение компилируется с помощью среды выполнения .NET Framework 4, но содержит библиотеку, построенную с помощью более старой среды выполнения, эта библиотека также будет использовать среду выполнения .NET Framework 4. Но, если приложение было создано с помощью более старой среды выполнения и библиотеки, которая построена в .NET Framework 4, приложение также необходимо явным образом настроить на использование .NET Framework 4 (см. [сценарий 3](#scenarios)).  
  
- **Разработчики управляемых COM-компонентов**. Управляемые COM-компоненты ранее автоматически выполнялись в последней версии среды выполнения, установленной на компьютере. Теперь COM-компоненты можно запускать в той версии среды выполнения, в которой они были созданы.  
  
     Как отражено в следующей таблице, созданные на платформе .NET Framework версии 1.1 компоненты могут запускаться параллельно с компонентами версии 4, но не могут выполняться вместе с компонентами версий 2.0, 3.0 или 3.5, так как параллельное размещение для этих версий невозможно.  
  
    |Версия платформы .NET Framework|1.1|2.0 - 3.5|4|  
    |----------------------------|---------|----------------|-------|  
    |1.1|Неприменимо|Нет|Да|  
    |2.0 - 3.5|Нет|Неприменимо|Да|  
    |4|Да|Да|Неприменимо|  
  
> [!NOTE]
> Версии платформы .NET Framework 3.0 и 3.5 созданы с помощью инкрементального построения на базе версии 2.0 и не требуют параллельного запуска. По сути они представляют собой одну и ту же версию.  
  
<a name="scenarios"></a>
## <a name="common-side-by-side-hosting-scenarios"></a>Общие сценарии параллельного размещения  
  
- **Сценарий 1.** Собственное приложение, которое использует COM-компоненты, созданные в более ранних версиях платформы .NET Framework.  
  
     Установленные версии платформы .NET Framework. .NET Framework 4 и все остальные версии платформы .NET Framework, используемые COM-компонентами.  
  
     Необходимые действия: в этой ситуации не следует предпринимать никаких действий. COM-компоненты будут выполняться в той версии платформы .NET Framework, в которой они были зарегистрированы.  
  
- **Сценарий 2**. Управляемое приложение, созданное в .NET Framework 2.0 с пакетом обновления 1 (SP1), можно запустить .NET Framework 4, если версия 2 отсутствует.  
  
     Установленные версии платформы .NET Framework. Более ранняя версия .NET Framework и .NET Framework 4.  
  
     Необходимые действия: откройте [файл конфигурации приложения](../configure-apps/index.md) в каталоге приложения и используйте [элемент \<startup>](../configure-apps/file-schema/startup/startup-element.md) и [элемент \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) следующим образом:  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- **Сценарий 3.** Собственное приложение, которое использует COM-компоненты, созданные в более ранних версиях платформы .NET Framework. При этом приложение необходимо запустить в .NET Framework 4.  
  
     Установленные версии платформы .NET Framework. .NET Framework 4.  
  
     Необходимые действия: откройте файл конфигурации приложения в каталоге приложения и используйте элемент `<startup>`, атрибут `useLegacyV2RuntimeActivationPolicy` которого имеет значение `true`, и набор элементов `<supportedRuntime>` следующим образом:  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере показан неуправляемый узел COM, в котором управляемый COM-компонент выполняется с помощью версии платформы .NET Framework, для которой был предназначен данный компонент.  
  
 Для выполнения следующего примера скомпилируйте и зарегистрируйте следующий управляемый компонент COM с помощью .NET Framework 3.5. Чтобы зарегистрировать компонент, в меню **Проект** выберите пункт **Свойства**, перейдите на вкладку **Сборка**, а затем установите флажок **Регистрация для COM-взаимодействия**.  
  
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
  
 Скомпилируйте следующее неуправляемое приложение C++, которое активирует COM-объект, созданный в предыдущем примере.  
  
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
  
## <a name="see-also"></a>См. также

- [Элемент \<startup>](../configure-apps/file-schema/startup/startup-element.md)
- [\<Поддерживаемый элемент среды выполнения](../configure-apps/file-schema/startup/supportedruntime-element.md)

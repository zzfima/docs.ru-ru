---
title: "Диагностика ошибок посредством управляемых помощников по отладке"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
caps.latest.revision: "63"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e23de3ea6e9693c05aa81da056ac7763bced8e9a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="diagnosing-errors-with-managed-debugging-assistants"></a>Диагностика ошибок посредством управляемых помощников по отладке
Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения. Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами. Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом. Вы можете включить или отключить все помощники отладки управляемого кода, добавив раздел в реестр Windows либо задав переменную среды. Вы можете включить отдельные помощники, используя параметры конфигурации приложения. Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения. Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения. Вы не сможете включить его для уже запущенных приложений.  
  
> [!NOTE]
>  При включении помощника отладки управляемого кода он остается активным даже тогда, когда ваш код в отладчике не выполняется. Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением. Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.  
  
> [!NOTE]
>  Когда ваш код выполняется в интегрированной среде разработки (IDE) Visual Studio, вы можете предотвратить появление диалогового окна исключения, отображаемого для определенных событий помощника отладки управляемого кода. Для этого в меню **Отладка** выберите **Исключения**. (Если в меню **Отладка** нет команды **Исключения**, щелкните **Настроить** в меню **Сервис** и добавьте ее.) В диалоговом окне **Исключения** разверните список **Помощники отладки управляемого кода** и снимите флажок **Вызванное** для отдельного помощника. Например, чтобы не отображать диалоговое окно исключения для [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md), снимите флажок **Вызванное** рядом с его именем в списке **Помощники отладки управляемого кода**. Вы также можете использовать это диалоговое окно для включения отображения диалоговых окон исключений помощников отладки управляемого кода.  
  
 В следующей таблице перечислены помощники отладки управляемого кода, входящие в состав .NET Framework.  
  
|||  
|-|-|  
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|  
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|  
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|  
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|  
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|  
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|  
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|  
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|  
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|  
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|  
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|  
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|  
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|  
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|  
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|  
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|  
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|  
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|  
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|  
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|  
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|  
  
 По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков. Вы можете просмотреть набор по умолчанию в Visual Studio, щелкнув **Исключения** в меню **Отладка** и развернув список **Помощники отладки управляемого кода**.  
  
## <a name="enabling-and-disabling-mdas"></a>Включение и отключение помощников отладки управляемого кода  
 Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения. Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.  
  
 В Visual Studio 2005 и более поздних версий при включении ведущего процесса вы не можете отключить помощники отладки управляемого кода, входящие в стандартный набор, или включить помощники, не входящие в этот набор. Ведущий процесс включен по умолчанию, поэтому его необходимо отключить явным образом.  
  
 Для отключения ведущего процесса в Visual Studio выполните одно из следующих действий:  
  
1.  Выберите проект в **обозревателе решений**.  
  
2.  В меню **Проект** выберите пункт **Свойства**.  
  
     Отображается окно **Конструктор проектов**.  
  
3.  Откройте вкладку **Отладка**.  
  
4.  В разделе **Включение отладчиков** снимите флажок **Включить ведущий процесс Visual Studio**.  
  
 Однако отключение ведущего процесса может негативно повлиять на производительность. Вы можете избежать необходимости отключать помощники, запретив Visual Studio отображать диалоговое окно помощника отладки управляемого кода при получении уведомления от помощника. Для этого щелкните **Исключения** в меню **Отладка**, разверните список **Помощники отладки управляемого кода** и затем установите или снимите флажок **Вызванное** для конкретного помощника.  
  
### <a name="enabling-and-disabling-mdas-by-using-a-registry-key"></a>Включение и отключение помощников отладки управляемого кода с помощью раздела реестра  
 Вы можете включить помощники, добавив в реестр Windows подраздел HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA (тип REG_SZ, значение 1). Скопируйте следующий пример в текстовый файл с именем MDAEnable.reg. Откройте редактор реестра Windows (RegEdit.exe) и затем в меню **Файл** выберите команду **Импорт**. Выберите файл MDAEnable.reg, чтобы включить помощники отладки управляемого кода на данном компьютере. Установка для подраздела строкового значения 1 (не значения DWORD, равного 1) позволяет считывать параметры помощника из файла *ИмяПриложения.суффикс*.mda.config. (Например, файл конфигурации помощника для Блокнота имел бы имя notepad.exe.mda.config)  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 Если на компьютере в 64-разрядной операционной системе выполнянется 32-разрядное приложение, раздел помощника нужно задать следующим образом:  
  
```  
      Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 Дополнительные сведения см. в разделе [Включение и отключение помощников отладки управляемого кода с помощью параметров конфигурации приложения](#appConfig). Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA. Дополнительные сведения см. в разделе [Включение и отключение помощников отладки управляемого кода с помощью переменной среды](#envVariable).  
  
 Чтобы отключить помощники отладки управляемого кода, задайте для подраздела помощников значение 0 (ноль) с помощью редактора реестра Windows.  
  
 По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра. Примерами таких помощников являются [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) и [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md). Эти помощники можно отключить, запустив файл MDADisable.reg в соответствии с приведенным выше описанием.  
  
<a name="envVariable"></a>   
### <a name="enabling-and-disabling-mdas-by-using-an-environment-variable"></a>Включение и отключение помощников отладки управляемого кода с помощью переменной среды  
 Активацией помощников также можно управлять с помощью переменной среды COMPLUS_MDA, которая переопределяет раздел реестра. Строка COMPLUS_MDA представляет собой разделенный точками с запятыми перечень имен помощников отладки управляемого кода или других специальных управляющих строк, составленный без учета регистра. При запуске под контролем управляемого или неуправляемого отладчика по умолчанию включается набор помощников. Для этого необходимо неявным образом добавить разделенный точками с запятыми список помощников, которые включаются по умолчанию под контролем отладчиков, в начало значения переменной среды или раздела реестра. Специальные управляющие строки:  
  
-   `0` — отключает все помощники.  
  
-   `1` — считывает параметры помощника из файла *ИмяПриложения*.mda.config.  
  
-   `managedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске управляемого исполняемого файла под контролем отладчика.  
  
-   `unmanagedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске неуправляемого исполняемого файла под контролем отладчика.  
  
 При наличии конфликтующих параметров более старые параметры переопределяются более новыми:  
  
-   `COMPLUS_MDA=0` отключает все помощники, включая те, которые неявно включаются под контролем отладчика.  
  
-   `COMPLUS_MDA=gcUnmanagedToManaged` включает `gcUnmanagedToManaged` в дополнение к помощникам, которые неявно включаются под контролем отладчика.  
  
-   `COMPLUS_MDA=0;gcUnmanagedToManaged` включает `gcUnmanagedToManaged`, но отключает те помощники, которые были бы неявно включены под контролем отладчика.  
  
<a name="appConfig"></a>   
### <a name="enabling-and-disabling-mdas-by-using-application-specific-configuration-settings"></a>Включение и отключение помощников отладки управляемого кода с помощью параметров конфигурации приложения  
 Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения. Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA. Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения. Имя файла имеет следующий вид *ИмяПриложения*.mda.config, например notepad.exe.mda.config. Помощники, включенные в файле конфигурации приложения, могут иметь атрибуты или элементы, предназначенные специально для управления данным аспектом работы помощника. В следующем примере показано, как включить и настроить [маршалинг](../../../docs/framework/debug-trace-profile/marshaling-mda.md).  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="*"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="*"/>  
      </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
 Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении. Помощник `Marshaling` также может фильтровать имена полей методов и структур, заданные в дочерних элементах `<methodFilter>` и `<fieldFilter>` соответственно.  
  
 В следующем примере показано, как включить несколько помощников отладки управляемого кода с помощью их параметров по умолчанию.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion />  
    <invalidCERCall />  
    <openGenericCERCall />  
    <virtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
> [!IMPORTANT]
>  При указании нескольких помощников в файле конфигурации их следует перечислять в алфавитном порядке. Например, если вы хотите включить помощники `virtualCERCall` и `invalidCERCall`, необходимо добавить запись `<invalidCERCall />` перед записью `<virtualCERCall />`. Если записи расположены не в алфавитном порядке, отображается сообщение о необработанном исключении недопустимого файла конфигурации.  
  
### <a name="mda-output"></a>Выходные данные помощников  
 Выходные данные помощников аналогичны следующему примеру, в котором приведены входные данные помощника `pInvokeStackImbalance`.  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## <a name="see-also"></a>См. также  
 [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)

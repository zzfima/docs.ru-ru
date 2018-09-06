---
title: Диагностика ошибок посредством управляемых помощников по отладке
ms.date: 08/14/2018
f1_keywords:
- EHMDA
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43740952"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Диагностика ошибок посредством управляемых помощников по отладке

Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения. Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами. Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом.

Вы можете [включить или отключить](#enable-and-disable-mdas) все помощники, добавив раздел в реестре Windows, или задав переменную среды. Вы можете включить отдельные помощники, используя параметры конфигурации приложения. Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения. Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения. Вы не сможете включить его для уже запущенных приложений.

В следующей таблице перечислены Помощники отладки управляемого кода, поставляемых вместе с .NET Framework:

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

По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков. Можно просмотреть набор по умолчанию в Visual Studio, выбрав **Windows** > **параметры исключений** на **Отладка** меню, а затем развернуть **Помощники отладки управляемого кода** списка.

![Окно параметров исключений в Visual Studio](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Включение и отключение помощников отладки управляемого кода

Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения. Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.

> [!TIP]
> Вместо отключения Помощники отладки управляемого кода, можно запретить отображение диалогового окна MDA при получении уведомления от Помощника Visual Studio. Чтобы сделать это, выберите **Windows** > **параметры исключений** на **Отладка** меню разверните **Помощники отладки управляемого кода**список, а затем установите или снимите **прервать при исключение** флажок для отдельного Помощника.

### <a name="registry-key"></a>Раздел реестра .

Чтобы включить Помощники отладки управляемого кода, добавьте **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\MDA** раздел реестра Windows (тип REG_SZ, значение 1). Скопируйте следующий пример в текстовый файл с именем *MDAEnable.reg*. Откройте редактор реестра Windows (RegEdit.exe) и из **файл** меню выберите команду **импорта**. Выберите *MDAEnable.reg* файл, чтобы включить Помощники отладки управляемого кода на этом компьютере. Установка для подраздела строкового значения **1** (не значения DWORD, равного **1**) позволяет считывать параметры Помощника из *имяПриложения.суффикс*. mda.config файл. Например файл конфигурации Помощника для блокнота бы имя notepad.exe.mda.config.

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

Если на компьютере в 64-разрядной операционной системе выполнянется 32-разрядное приложение, раздел помощника нужно задать следующим образом:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

См. в разделе [параметров конфигурации конкретных приложений](#application-specific-configuration-settings) Дополнительные сведения. Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA. См. в разделе [переменной среды](#environment-variable) Дополнительные сведения.

Чтобы отключить Помощники отладки управляемого кода, задайте для подраздела Помощников **0** (ноль), с помощью редактора реестра Windows.

По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра. Эти помощники можно отключить, выполнив *MDADisable.reg* файл, как описано выше в этом разделе.

### <a name="environment-variable"></a>Переменная среды

Активацией помощников также можно управлять с помощью переменной среды COMPLUS_MDA, которая переопределяет раздел реестра. Строка COMPLUS_MDA представляет собой разделенный точками с запятыми перечень имен помощников отладки управляемого кода или других специальных управляющих строк, составленный без учета регистра. При запуске под контролем управляемого или неуправляемого отладчика по умолчанию включается набор помощников. Для этого необходимо неявным образом добавить разделенный точками с запятыми список помощников, которые включаются по умолчанию под контролем отладчиков, в начало значения переменной среды или раздела реестра. Специальные управляющие строки:

- `0` — отключает все помощники.

- `1` — считывает параметры помощника из файла *ИмяПриложения*.mda.config.

- `managedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске управляемого исполняемого файла под контролем отладчика.

- `unmanagedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске неуправляемого исполняемого файла под контролем отладчика.

При наличии конфликтующих параметров более старые параметры переопределяются более новыми:

- `COMPLUS_MDA=0` отключает все помощники, включая те, которые неявно включаются под контролем отладчика.

- `COMPLUS_MDA=gcUnmanagedToManaged` включает `gcUnmanagedToManaged` в дополнение к помощникам, которые неявно включаются под контролем отладчика.

- `COMPLUS_MDA=0;gcUnmanagedToManaged` включает `gcUnmanagedToManaged`, но отключает те помощники, которые были бы неявно включены под контролем отладчика.

### <a name="application-specific-configuration-settings"></a>Параметры конфигурации для конкретного приложения

Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения. Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA. Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения. Имя файла имеет следующий вид *ИмяПриложения*.mda.config, например notepad.exe.mda.config. Помощники, включенные в файле конфигурации приложения, могут иметь атрибуты или элементы, предназначенные специально для управления данным аспектом работы помощника.

В следующем примере показано, как включить и настроить [маршалинг](../../../docs/framework/debug-trace-profile/marshaling-mda.md):

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

Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении. `Marshaling` MDA можно также фильтровать имена метода и структурным полям **methodFilter** и **fieldFilter** дочерние элементы, соответственно.

В следующем примере показано, как включить несколько помощников отладки управляемого кода с помощью их параметров по умолчанию:

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
> При указании нескольких помощников в файле конфигурации их следует перечислять в алфавитном порядке. Например, если вы хотите включить помощники `virtualCERCall` и `invalidCERCall`, необходимо добавить запись `<invalidCERCall />` перед записью `<virtualCERCall />`. Если записи расположены не в алфавитном порядке, отображается сообщение о необработанном исключении недопустимого файла конфигурации.

## <a name="mda-exceptions"></a>Исключения по отладке управляемого кода

Если MDA включен, он остается активным даже когда ваш код не выполняется в режиме отладки. Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением. Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.

Если код выполняется в среде разработки Visual Studio (IDE), можно предотвратить диалоговое окно исключения, который отображается для определенных событий по отладке управляемого кода. Для этого на **Отладка** меню, выберите **Windows** > **параметры исключений**. В **параметры исключений** окне разверните **Помощники отладки управляемого кода** списке, а затем снимите **прервать при исключение** флажок для отдельного Помощника. Можно также использовать это диалоговое окно, чтобы *включить* отображение диалоговых окон исключений по отладке управляемого кода.

## <a name="mda-output"></a>Выходные данные помощников

MDA результат аналогичен приведенному в следующем примере показаны выходные данные `PInvokeStackImbalance` по отладке управляемого кода:

**Вызов функции PInvoke "MDATest! MDATest.Program::StdCall "внесла дисбаланс в стек. Это обусловлено тем, скорее всего, управляемая сигнатура PInvoke не соответствует сигнатуре неуправляемого целевой. Проверьте, что соглашение о вызовах и параметры подписи PInvoke соответствовать неуправляемой сигнатуре целевой объект.**

## <a name="see-also"></a>См. также

- [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)

---
title: Диагностика ошибок посредством помощников по отладке управляемого кода
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
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216556"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Диагностика ошибок с помощью помощников по отладке управляемого кода

Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения. Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами. Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом.

Вы можете [включить или отключить](#enable-and-disable-mdas) все MDA, добавив ключ в реестр Windows или задав переменную среды. Вы можете включить отдельные помощники, используя параметры конфигурации приложения. Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения. Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения. Вы не сможете включить его для уже запущенных приложений.

В следующей таблице перечислены MDA, поставляемые с .NET Framework.

|||
|-|-|
|[asynchronousThreadAbort](asynchronousthreadabort-mda.md)|[bindingFailure](bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](dirtycastandcalloninterface-mda.md)|[disconnectedContext](disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](failedqi-mda.md)|[fatalExecutionEngineError](fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](invalidapartmentstatechange-mda.md)|
|[invalidCERCall](invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](invalidgchandlecookie-mda.md)|[invalidIUnknown](invalidiunknown-mda.md)|
|[invalidMemberDeclaration](invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](invalidvariant-mda.md)|[jitCompilationStart](jitcompilationstart-mda.md)|
|[loaderLock](loaderlock-mda.md)|[loadFromContext](loadfromcontext-mda.md)|
|[marshalCleanupError](marshalcleanuperror-mda.md)|[marshaling](marshaling-mda.md)|
|[memberInfoCacheCreation](memberinfocachecreation-mda.md)|[moduloObjectHashcode](moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](noncomvisiblebaseclass-mda.md)|[notMarshalable](notmarshalable-mda.md)|
|[openGenericCERCall](opengenericcercall-mda.md)|[overlappedFreeError](overlappedfreeerror-mda.md)|
|[pInvokeLog](pinvokelog-mda.md)|[pInvokeStackImbalance](pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](raceonrcwcleanup-mda.md)|[reentrancy](reentrancy-mda.md)|
|[releaseHandleFailed](releasehandlefailed-mda.md)|[reportAvOnComRelease](reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](streamwriterbuffereddatalost-mda.md)|[virtualCERCall](virtualcercall-mda.md)|

По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков. Вы можете просмотреть набор по умолчанию в Visual Studio, выбрав пункт **параметры исключений** **Windows** > в меню **Отладка** , а затем развернув список **помощники по отладке управляемого** кода.

![Окно параметров исключений в Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Включение и отключение MDA

Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения. Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.

> [!TIP]
> Вместо отключения MDA можно запретить Visual Studio отображать диалоговое окно MDA при получении уведомления MDA. Для этого выберите пункт **параметры исключений** **Windows** > в меню **Отладка** , разверните список **помощники по отладке управляемого** кода, а затем установите или снимите флажок **прерывать при возникновении** для отдельного MDA.

### <a name="registry-key"></a>Ключ реестра

Чтобы включить MDA, добавьте **HKEY_LOCAL_MACHINE \софтваре\микрософт\\. Подраздел Нетфрамеворк\мда** (введите REG_SZ, значение 1) в реестре Windows. Скопируйте следующий пример в текстовый файл с именем *мдаенабле. reg*. Откройте редактор реестра Windows (regedit. exe) и в меню **файл** выберите пункт **Импорт**. Выберите файл *мдаенабле. reg* , чтобы включить MDA на этом компьютере. При установке подраздела в строковое значение **1** (а не значение DWORD, равное **1**) включает чтение параметров MDA из файла *ApplicationName. суффикс*. MDA. config. Например, файл конфигурации MDA для блокнота будет называться Notepad. exe. MDA. config.

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

Дополнительные сведения см. в разделе [Параметры конфигурации, относящиеся к приложению](#application-specific-configuration-settings) . Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA. Дополнительные сведения см. в разделе [переменная среды](#environment-variable) .

Чтобы отключить MDA, присвойте подразделу MDA значение **0** (ноль) с помощью редактора реестра Windows.

По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра. Эти помощники можно отключить, запустив файл *мдадисабле. reg* , как описано выше в этом разделе.

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

Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения. Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA. Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения. Имя файла имеет форму *applicationName*. MDA. config; Например, Notepad. exe. MDA. config. У помощников, включенных в файле конфигурации приложения, могут быть атрибуты или элементы, специально предназначенные для управления поведением этого помощника.

В следующем примере показано, как включить и настроить [упаковку](marshaling-mda.md):

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

Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении. `Marshaling` MDA также может фильтровать имена методов и полей структуры, предоставляемых в дочерних элементах **месодфилтер** и **фиелдфилтер** соответственно.

В следующем примере показано, как включить несколько MDA с помощью параметров по умолчанию.

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

## <a name="mda-exceptions"></a>Исключения MDA

Если MDA включен, он активен даже в том случае, если код не выполняется в отладчике. Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением. Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.

Когда код выполняется в интегрированной среде разработки Visual Studio (IDE), можно избежать диалогового окна исключения, которое отображается для конкретных событий MDA. Для этого в меню **Отладка** выберите пункт **параметры исключений** **Windows** > . В окне **параметры исключений** разверните список **помощники по отладке управляемого** кода, а затем снимите флажок **прерывать при возникновении** для отдельного MDA. Это диалоговое окно также можно использовать, чтобы *включить* отображение диалоговых окон исключений MDA.

## <a name="mda-output"></a>Выходные данные помощников

Выходные данные MDA похожи на приведенный ниже пример, который показывает выходные данные `PInvokeStackImbalance` MDA:

**Вызов функции PInvoke "Мдатест! Мдатест. Program:: StdCall ' имеет несбалансированный стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**

## <a name="see-also"></a>См. также:

- [Отладка, трассировка и профилирование](index.md)

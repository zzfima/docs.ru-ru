---
title: Практическое руководство. Отладка проблем при активации CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 602ee3c88237a902d48339836fbe25f636ae9705
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716508"
---
# <a name="how-to-debug-clr-activation-issues"></a>Практическое руководство. Отладка проблем при активации CLR

При возникновении проблем при попытке запустить приложение с правильной версией среды CLR можно просматривать и отлаживать журналы активации среды CLR. Эти журналы могут быть очень полезными при выявлении основной причины проблемы активации, когда приложение или загружает не ту версию среды CLR, которую ожидалось, или вообще не загружает среду CLR. В разделе [Ошибки инициализации платформы .NET Framework: управление пользовательской средой](initialization-errors-managing-the-user-experience.md) рассматривается случай, когда среда CLR не была найдена.

Ведение журналов активации среды CLR может быть включено для всей системы с помощью раздела реестра HKEY_LOCAL_MACHINE или переменной среды операционной системы. Журнал будет вестись до тех пор, пока запись реестра или переменная среды не будет удалена. Кроме того, можно использовать переменную среды процесса, чтобы включить ведение журнала с иными областью и временем существования.

Журналы активации среды CLR не следует путать с [журналами привязки сборок](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), которые полностью отличаются.

## <a name="to-enable-clr-activation-logging"></a>Включение ведения журналов активации среды CLR

### <a name="using-the-registry"></a>Использование реестра

1. В редакторе реестра перейдите к разделу HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (на 32-разрядном компьютере) или HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (на 64-разрядном компьютере).

2. Добавьте строковое значение с именем `CLRLoadLogDir` и задайте в нем полный путь к существующему каталогу, в котором будут храниться журналы активации среды CLR.

Журналы активации будут вестись до тех пор, пока не вы удалите это строковое значение.

### <a name="using-an-environment-variable"></a>Использование переменной среды

- Задайте в переменной среды `COMPLUS_CLRLoadLogDir` строку, представляющую полный путь к существующему каталогу, в котором будут храниться журналы активации среды CLR.

    Способ задания переменной среды определяет ее область действия:

  - Если переменная задается на уровне системы, ведение журналов активации включается для всех приложений платформы .NET Framework на этом компьютере до тех пор, пока переменная среды не будет удалена.

  - Если она задана на уровне пользователя, ведение журналов активации включается только для учетной записи текущего пользователя. Ведение журналов продолжается до тех пор, пока переменная среды не будет удалена.

  - Если переменная задается из процесса перед загрузкой среды CLR, журналы активации будут вестись до завершения процесса.

  - Если переменная задана из командной строки перед запуском приложения, журналы активации будут вестись для всех приложений, запущенных из этой командной строки.

    Например, чтобы хранить журналы активации в каталоге c:\clrloadlogs с областью действия уровня процесса, следует открыть окно командной строки и ввести следующую строку перед запуском приложения:

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a>Пример

Журналы активации среды CLR предоставляют большой объем данных об активации среды CLR и использовании API размещения среды CLR. Большая часть этих данных используется внутренне Майкрософт, но некоторые из данных также могут быть полезны для разработчиков, как описано в этой статье.

Журнал автоматически устанавливает порядок, в котором были вызваны API размещения среды CLR. Он также содержит полезные данные о наборе установленных сред выполнения, обнаруженных на компьютере. Формат самого журнала активации среды CLR не документирован, но может быть использован для помощи разработчикам, которым требуется разрешить проблемы активации среды CLR.

> [!NOTE]
> Нельзя открыть журнал активации до тех пор, пока процесс, использующий среду CLR, не был завершен.

> [!NOTE]
> Журналы активации среды CLR не локализуются; они всегда создаются на английском языке.

В следующем примере журналов активации наиболее полезные сведения выделены и описаны после журнала.

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- **CLR Loading log** указывает путь до исполняемого файла, запустившего процесс, который загружает управляемый код. Обратите внимание, что это может быть собственное основное приложение.

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- **Installed Runtime** — набор версий среды CLR, установленных на компьютере, являющихся кандидатами для запроса активации.

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- **built with version** — версия среды CLR, которая использовалась для построения бинарного файла, который был предоставлен методу, подобному [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- **feature-on-demand installation** указывает на включение .NET Framework 3.5 в Windows 8. См. в разделе [Ошибки инициализации платформы .NET Framework: управление пользовательской средой](initialization-errors-managing-the-user-experience.md) дополнительные сведения об этом случае.

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a>См. также

- [Развертывание](index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)

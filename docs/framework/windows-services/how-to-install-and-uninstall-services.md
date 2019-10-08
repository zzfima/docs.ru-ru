---
title: Практическое руководство. Установка и удаление служб Windows
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 38fc0172b5f97561d69fe495237e95597d7b9727
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003133"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Практическое руководство. Установка и удаление служб Windows

При разработке службы Windows с .NET Framework можно быстро установить приложение службы с помощью программы командной строки [*Installutil. exe*](../tools/installutil-exe-installer-tool.md) или [PowerShell](/powershell/scripting/overview). Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield. Дополнительные сведения см. в разделе [Создание пакета установщика (клиент Windows)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

> [!WARNING]
> Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье. Вместо этого определите, какая программа (или программный пакет) установила эту службу, а затем выберите **Приложения** в параметрах, чтобы удалить эту программу. Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.

Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows. Дополнительные сведения см. в разделе [Пошаговое руководство: создание диспетчера служб Windows](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).

Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5. Перед запуском проекта необходимо установить службу в проекте.

> [!TIP]
> Запустите **обозреватель сервера** и убедитесь, что служба установлена или удалена. Дополнительные сведения см. в разделе [Практическое руководство. Использование обозревателя сервера в Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).

### <a name="install-your-service-manually-using-installutilexe-utility"></a>Установка службы вручную с помощью программы InstallUtil. exe

1. В меню **Пуск** выберите каталог **Visual Studio \<*версия*>** , а затем выберите **Командная строка разработчика для VS \<*версия*>** .

     Появится командная строка разработчика для Visual Studio.

2. Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.

3. Запустите *InstallUtil.exe* из командной строки, указав исполняемый файл проекта в качестве параметра:

    ```console
    installutil <yourproject>.exe
    ```

     Если вы используете командную строку разработчика для Visual Studio, системный путь должен указывать на файл *InstallUtil.exe*. Если это не так, можно добавить его в путь или использовать полный путь для его вызова. Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%WINDIR%\Microsoft.NET\Framework[64]\\<версия_платформы\>* .

     Пример:
     - Для 32-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: если каталог установки Windows — *C:\Windows*, по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Для 64-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a>Удаление службы вручную с помощью программы InstallUtil. exe

1. В меню **Пуск** выберите каталог **Visual Studio \<*версия*>** , а затем выберите **Командная строка разработчика для VS \<*версия*>** .

     Появится командная строка разработчика для Visual Studio.

2. Запустите *InstallUtil.exe* из командной строки, указав выходные данные проекта в качестве параметра:

    ```console
    installutil /u <yourproject>.exe
    ```

3. После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).

### <a name="install-your-service-manually-using-powershell"></a>Установка службы вручную с помощью PowerShell

1. В меню **Пуск** выберите каталог **Windows PowerShell** , а затем выберите **Windows PowerShell**.

2. Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.

3. Запустите командлет [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) с параметром, указав выходные данные проекта, и имя службы в качестве параметров:

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a>Удаление службы вручную с помощью PowerShell

1. В меню **Пуск** выберите каталог **Windows PowerShell** , а затем выберите **Windows PowerShell**.

2. Выполните командлет [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) с именем службы в качестве параметра:

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](../windows-services/introduction-to-windows-service-applications.md)
- [Практическое руководство. Создание служб Windows](../windows-services/how-to-create-windows-services.md)
- [Практическое руководство. Добавление установщиков в приложение-службу](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (установщик)](../tools/installutil-exe-installer-tool.md)

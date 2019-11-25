---
title: Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e07bb3443fb9461fa707d66e74350a39980c60c0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975556"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a>Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5

.NET Framework 4.5 — это распространяемый пакет среды выполнения. Если вы разрабатываете приложения для данной версии платформы .NET Framework, можно включить (присоединить к цепочке) установку .NET Framework 4.5 в качестве необходимого компонента при установке приложения. Для создания специальной или универсальной процедуры установки может потребоваться автоматический запуск и отслеживание процесса установки .NET Framework 4.5 с одновременным отображением собственного представления хода выполнения установки. Для включения отслеживания в автоматическом режиме установка .NET Framework 4.5, которая может находиться под наблюдением, определяет протокол с помощью сегмента памяти ввода-вывода (MMIO) для связи с вашей установкой (наблюдателем или формирователем цепочки). Этот протокол определяет способ, которым формирователь цепочки получает информацию о ходе выполнения, получает подробные результаты, отвечает на сообщения и отменяет установку .NET Framework 4.5.

- **Вызов**. Чтобы вызвать процесс установки .NET Framework 4.5 и получать информацию о ходе выполнения из раздела MMIO, программа установки приложения должна выполнить следующие действия:

    1. Вызовите распространяемую программу .NET Framework 4.5:

        `dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name`

        Где *section name* — любое имя, которое вы хотите использовать для идентификации приложения. Установка .NET Framework выполняет чтение из раздела MMIO и запись в раздел MMIO асинхронно, поэтому в течение этого времени удобно использовать события и сообщения. В этом примере процесс установки .NET Framework создан конструктором, который выделяет раздел MMIO (`TheSectionName`) и указывает событие (`TheEventName`):

        ```cpp
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        Эти имена следует заменить на имена, уникальные для программы установки приложения.

    2. Чтение из раздела MMIO. На платформе .NET Framework 4.5 операции скачивания и установки выполняются одновременно: один компонент .NET Framework может устанавливаться, в то время как другой еще скачивается. В результате данные о ходе выполнения отправляются назад (записываются) в раздел MMIO в виде двух чисел (`m_downloadSoFar` и `m_installSoFar`), значение которых увеличивается от 0 до 255. Когда записано число 255 и .NET Framework завершает работу, установка завершается.

- **Коды выхода**. Следующие коды выхода от команды вызова распространяемой программы .NET Framework 4.5 указывают, успешно ли выполнена установка:

  - 0 — установка выполнена успешно.

  - 3010 — установка выполнена успешно; необходима перезагрузка системы.

  - 1602 — установка отменена.

  - Все другие коды — в процессе установки произошли ошибки; для получения подробных сведений просмотрите файлы журналов, созданные в папке %temp%.

- **Отмена установки**. Установку можно в любое время отменить, используя метод `Abort` для установки флагов `m_downloadAbort` и`m_ installAbort` в разделе MMIO.

## <a name="chainer-sample"></a>Пример формирователя цепочки

Пример формирователя цепочки автоматически запускает и отслеживает установку .NET Framework 4.5, при этом отображая ход выполнения. Этот пример похож на пример формирователя цепочки, предоставленный для платформы .NET Framework 4. Кроме того, он может избежать перезапуска системы путем обработки диалогового окна закрытия приложения платформы .NET Framework 4. Дополнительные сведения об этом окне сообщения см. в разделе [Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5](reducing-system-restarts.md). Этот пример можно использовать и с установщиком платформы .NET Framework 4; в этом случае сообщение просто не будет отправлено.

> [!WARNING]
> Этот пример следует запускать от имени администратора.

Можно загрузить полное решение для Visual Studio, [Пример формирователя цепочки .NET Framework 4.5](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba), из галереи примеров MSDN.

В следующих разделах описываются важные файлы в данном примере: MMIOChainer.h, ChainingdotNet4.cpp и IProgressObserver.h.

#### <a name="mmiochainerh"></a>MMIOChainer.h

- Файл MMIOChainer.h (см. [полный код](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) содержит определение структуры данных и базовый класс, из которого должен быть получен класс формирователя цепочки. .NET Framework 4.5 расширяет структуру данных MMIO для обработки данных, необходимых установщику .NET Framework 4.5. Изменения в структуре MMIO обладают обратной совместимостью, поэтому формирователь цепочки платформы .NET Framework 4 может работать с установкой платформы .NET Framework 4.5 без необходимости повторной компиляции. Но этот сценарий не поддерживает функцию для уменьшения перезапусков системы.

    Поле версии предоставляет средства для определения изменений структуры и формата сообщения. Установка платформы .NET Framework определяет версию интерфейса формирователя цепочки путем вызова функции `VirtualQuery` для определения размера сопоставления файлов. Если размер достаточно большой, чтобы вместить поле версии, то установка платформы .NET Framework использует указанное значение. Если сопоставление файлов слишком мало для хранения поля версии, как в варианте с платформой .NET Framework 4, то процесс установки предполагает версию 0 (4). Если формирователь цепочки не поддерживает версию сообщения, которое хочет отправить установка платформы .NET Framework, то установка платформы .NET Framework отвечает игнорированием.

    Структура данных MMIO определяется следующим образом:

    ```cpp
    // MMIO data structure for interprocess communication
        struct MmioDataStructure
        {
            bool m_downloadFinished;               // Is download complete?
            bool m_installFinished;                // Is installation complete?
            bool m_downloadAbort;                  // Set to cause downloader to abort.
            bool m_installAbort;                   // Set to cause installer to abort.
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.
            HRESULT m_hrInternalError;
            WCHAR m_szCurrentItemStep[MAX_PATH];
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.

            BYTE m_version;                        // Version of the data structure, set by chainer:
                                                   // 0x0: .NET Framework 4
                                                   // 0x1: .NET Framework 4.5

            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.
        };
    ```

- Структура данных `MmioDataStructure` не должна использоваться напрямую; вместо этого для реализации формирователя цепочки следует использовать класс `MmioChainer`. Создайте класс, производный от класса `MmioChainer`, для привязки распространяемого пакета .NET Framework 4.5.

#### <a name="iprogressobserverh"></a>IProgressObserver.h

- Файл IProgressObserver.h реализует наблюдатель хода выполнения (см. [полный код](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)). Этот наблюдатель получает уведомления о ходе выполнения загрузки и установки (определяется как `char`, 0–255, указывающее степень завершения 1 %–100 %). Наблюдатель также получает уведомления, когда элемент цепочки отправляет сообщение, и наблюдатель должен отправить ответ.

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a>ChainingdotNet4.5.cpp

- Файл [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) реализует класс `Server`, унаследованный от класса `MmioChainer`, и переопределяет соответствующие методы для отображения информации о ходе выполнения. MmioChainer создает раздел с указанным именем раздела и инициализирует формирователь цепочки с указанным именем события. Имя события сохраняется в сопоставленной структуре данных. Имена раздела и событий должны быть уникальными. Класс `Server` в следующем коде запускает указанную программу установки, отслеживает ход ее выполнения и возвращает код выхода.

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    Программа установки запускается в методе Main.

    ```cpp
    // Main entry point for program
    int __cdecl main(int argc, _In_count_(argc) char **_argv)
    {
        int result = 0;
        CString args;
        if (argc > 1)
        {
            args = CString(_argv[1]);
        }

        if (IsNetFx4Present(NETFX45_RC_REVISION))
        {
            printf(".NET Framework 4.5 is already installed");
        }
        else
        {
            result = Server().Launch(args);
        }

        return result;
    }
    ```

- Перед запуском программы установки формирователь цепочки проверяет, не установлена ли уже .NET Framework 4.5, с помощью вызова `IsNetFx4Present`:

    ```cpp
    ///  Checks for presence of the .NET Framework 4.
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.
    #define NETFX40_FULL_REVISION 0
    // TODO: Replace with released revision number
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5
    bool IsNetFx4Present(DWORD dwMinimumRelease)
    {
        DWORD dwError = ERROR_SUCCESS;
        HKEY hKey = NULL;
        DWORD dwData = 0;
        DWORD dwType = 0;
        DWORD dwSize = sizeof(dwData);

        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);
        if (ERROR_SUCCESS == dwError)
        {
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);

            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))
            {
                dwError = ERROR_INVALID_DATA;
            }
            else if (ERROR_FILE_NOT_FOUND == dwError)
            {
                // Release value was not found, let's check for 4.0.
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);

                // Install = (REG_DWORD)1;
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))
                {
                    // treat 4.0 as Release = 0
                    dwData = 0;
                }
                else
                {
                    dwError = ERROR_INVALID_DATA;
                }
            }
        }

        if (hKey != NULL)
        {
            ::RegCloseKey(hKey);
        }

        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));
    }
    ```

- Можно изменить путь к исполняемому файлу (Setup.exe в примере) в методе `Launch`, чтобы он указывал на правильное расположение, или настроить код для определения расположения. Базовый класс `MmioChainer` предоставляет блокирующий метод `Run()`, который вызывается производным классом.

    ```cpp
    bool Launch(const CString& args)
    {
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run
    STARTUPINFO si = {0};
    si.cb = sizeof(si);
    PROCESS_INFORMATION pi = {0};

    // Launch the Setup.exe that installs the .NET Framework 4.5
    BOOL bLaunchedSetup = ::CreateProcess(NULL,
     cmdline.GetBuffer(),
     NULL, NULL, FALSE, 0, NULL, NULL,
     &si,
     &pi);

    // If successful
    if (bLaunchedSetup != 0)
    {
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);
    Run(pi.hProcess, observer);

    ……………………..
    return (bLaunchedSetup != 0);
    }
    ```

- Метод `Send` перехватывает и обрабатывает сообщения. В данной версии платформы .NET Framework поддерживается только сообщение о закрытии приложения.

    ```cpp
            // SendMessage
            //
            // Send a message and wait for the response.
            // dwMessage: Message to send
            // pData: The buffer to copy the data to
            // dwDataLength: Initially a pointer to the size of pBuffer. Upon successful call, the number of bytes copied to pBuffer.
            //--------------------------------------------------------------
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)
        {
            DWORD dwResult = 0;
            printf("received message: %d\n", dwMessage);
            // Handle message
            switch (dwMessage)
            {
            case MMIO_CLOSE_APPS:
                {
                    printf("    applications are holding files in use:\n");
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)
                    {
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);
                    }

                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");
                    while (dwResult == 0)
                    {
                        switch (toupper(getwchar()))
                        {
                        case 'Y':
                            dwResult = IDYES;  // Close apps
                            break;
                        case 'N':
                            dwResult = IDNO;
                            break;
                        case 'R':
                            dwResult = IDRETRY;
                            break;
                        }
                    }
                    printf("\n");
                    break;
                }
            default:
                break;
            }
            printf("  response: %d\n  ", dwResult);
            return dwResult;
        }
    };
    ```

- Данные о ходе выполнения хранятся в переменной типа `char` без знака от 0 (0 %) до 255 (100 %).

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- HRESULT передается методу `Finished`.

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > Распространяемый пакет .NET Framework 4.5 обычно записывает много сообщений о ходе выполнения и одно сообщение, указывающее о завершении (на стороне формирователя цепочки). Он также выполняет асинхронное чтение, осуществляя поиск записи `Abort`. Если он получает запись `Abort`, то отменяет установку и записывает завершенную запись с E_ABORT как его данные после прерывания установки и отката операции установки.

Типовой сервер создает случайное имя файла MMIO, создает файл (как показано в предыдущем примере кода в `Server::CreateSection`) и запускает распространяемый пакет с помощью метода `CreateProcess`, передавая имя канала с параметром `-pipe someFileSectionName`. Сервер должен реализовать методы `OnProgress`, `Send` и `Finished` с кодом, характерным для пользовательского интерфейса приложения.

## <a name="see-also"></a>См. также

- [Руководство по развертыванию для разработчиков](deployment-guide-for-developers.md)
- [Развертывание](index.md)

---
title: Troubleshoot Начало начала с Windows Communication Foundation учебники
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 92e986370fe1b6e067d9f8aebc73179c1ac6a20f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183094"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Troubleshoot Начало начала с Windows Communication Foundation учебники

В этой статье содержатся решения наиболее распространенных проблем и ошибок, с которыми вы можете столкнуться при следовании за шагами в [учебнике: Начало работы с приложениями Windows Communication Foundation.](getting-started-tutorial.md)
  
## <a name="common-problems"></a>Распространенные проблемы

**Я не могу найти файлы проекта на жестком диске.**

 Visual Studio сохраняет файлы проекта в *C: «Имя\\&lt;&gt;пользователя »источник» (*  

**Я не могу найти файл *App.config,* созданный *Svcutil.exe*.**

 В Visual Studio окно **Add Existing Item** отображает только файлы со следующими расширениями по умолчанию:

- *.cs*
- *.resx*
- *.настройки*
- *.xsd*
- *.wsdl*

Чтобы отобразить все типы файлов, выберите **все файлы\*(.\*)** в списке выпадающих в нижнем правом углу окна **Добавить существующий элемент.**  
  
## <a name="common-errors"></a>Распространенные ошибки

### <a name="compile-the-service-application"></a>Составить приложение службы

**Ошибка BC30420 'Sub Main' не была найдена в 'GettingStartedHost.Module1'.**

Точка входа неверна для приложения Visual Basic. Внести следующее изменение:

   1. В окне **Solution Explorer** выберите папку **GettingStartedHost,** а затем выберите **свойства** из меню ярлыка.
    а. В окне **GettingStartedHost** для **объекта запуска**выберите **Service.Program** (или точку входа для конкретного приложения) из списка.
    b. Из основного меню выберите **Файл** > **Сохранить все**.

### <a name="run-the-service-application"></a>Выполнить приложение службы

**HTTP не может зарегистрировать\/URL'http: /':8000/GettingStarted/CalculatorService'. Ваш процесс не имеет прав доступа к этому пространству имен.**

 Для правильного доступа начните процесс размещения службы Windows Communication Foundation (WCF) с административными привилегиями:

- Для Visual Studio: Выберите программу Visual Studio в меню **«Пуск»,** а затем выберите **More** > Run в**качестве администратора** из меню ярлыка.
- Для окна консоли: Выберите **командный запрос** в меню **«Пуск»,** а затем выберите **More** > **Run в качестве администратора** из меню ярлыка.
- Для Windows Explorer: Выберите исполняемый, а затем выберите Run в **качестве администратора** из меню ярлыка.

### <a name="compile-the-client-application"></a>Составить клиентское приложение

**'CalculatorClient', не содержит определения\<"имя метода>"\<и не метод расширения "имя метода>", принимая первый аргумент типа 'CalculatorClient' может быть найден (вы отсутствуете использование директивы или сборки ссылки?)**  

Только те методы, которые `ServiceOperationAttribute` вы отмечаете с атрибутом, публично разоблачаются. Если вы не `ServiceOperationAttribute` упускаете `ICalculator` атрибут из метода в интерфейсе, вы получаете это сообщение об ошибке во время компиляции.  

**Тип или имя имя 'CalculatorClient' не могут быть найдены (вы отсутствуете использование директивы или сборки ссылки?)**

 Вы получаете эту ошибку, если вы не добавляете *generatedProxy.cs* (или *сгенерированныйProxy.vb)* файл в свой клиентский проект, когда вы создали их с помощью инструмента *Svcutil.exe.*  

### <a name="run-the-client-application"></a>Запуск клиентского приложения

**Необработанное исключение: System.ServiceModel.EndpointNotFoundException: Не удалось\/подключиться к 'http: /localhost:8000/GettingStarted/CalculatorService'. Код ошибки TCP 10061: Подключение не может быть сделано, потому что целевая машина активно отказалась от него.**

Эта ошибка возникает при запуске клиентского приложения без предварительного запуска службы. Сначала запустите приложение хоста, чтобы запустить службу, а затем запустите клиентское приложение.

### <a name="use-the-svcutilexe-tool"></a>Используйте инструмент Svcutil.exe

**'Svcutil' не признается как внутренняя или внешняя команда, оперативная программа или пакетный файл.**

 *Svcutil.exe* должен быть на пути системы. Проще всего использовать запрос команды Visual Studio. Из меню **«Пуск»** выберите **версию Visual Studio \<>** каталоге, а затем выберите **подсказку команды разработчиков для версии VS \<>. ** Эта команда подсказывает системный путь к правильным местоположениям для всех инструментов, отправленных в рамках Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Запуск сервисных и клиентских приложений

**System.ServiceModel.SecurityNegotiationException: SOAP переговоров по безопасности с "http:\//localhost:8000/GettingStarted/CalculatorService" для целевой "http:\//localhost:8000/GettingStarted/CalculatorService' не удалось**  

Эта ошибка возникает на компьютере, подключенном к домену, который не имеет сетевого подключения. Подключите компьютер к сети или отключите безопасность как для службы, так и для клиента.

Чтобы отключить безопасность:

- Для службы замените код, `WSHttpBinding` который создает следующий код:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Для клиента в файле конфигурации обновите элемент ** \<безопасности>** под ** \<элементом связывания>** следующим образом:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>См. также раздел  
 [Начало работы с приложениями WCF](getting-started-tutorial.md)  
 [Быстрый запуск wCF для устранения неполадок](wcf-troubleshooting-quickstart.md)  
 [Проблемы с настройкой устранения неполадок](troubleshooting-setup-issues.md)

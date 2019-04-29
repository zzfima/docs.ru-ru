---
title: Устранение неполадок с Get к работе с Windows Communication Foundation учебники
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 8089e0fee262d07be591069982b1aacfbeae2521
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791473"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Устранение неполадок с Get к работе с Windows Communication Foundation учебники

В этой статье предоставляет решения для наиболее распространенных проблем и ошибок, которые могут возникнуть при выполнении действия, описанные в [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md). 
  
## <a name="common-problems"></a>Распространенные проблемы

**Не удается найти файлы проекта на жестком диске.**

 Visual Studio сохраняет файлы проекта в *C:\Users\\&lt;имя пользователя&gt;\source\repos*.  

**Не удается найти *App.config* файла, созданного *Svcutil.exe*.**

 В Visual Studio **добавить существующий элемент** окна отображаются только файлы со следующими расширениями по умолчанию: 
- *.cs* 
- *.resx* 
- *.Settings*
- *.xsd* 
- *.wsdl*

Чтобы отобразить все типы файлов, выберите **все файлы (\*.\*)**  в раскрывающемся списке в правом нижнем углу **добавить существующий элемент** окна.  
  
## <a name="common-errors"></a>Распространенные ошибки

### <a name="compile-the-service-application"></a>Компиляция приложения службы 

**Ошибка BC30420 «Sub Main» не найден в «GettingStartedHost.Module1».**

Точкой входа является неправильным для приложения Visual Basic. Внесите следующие изменения:

   1. В **обозревателе решений** выберите **GettingStartedHost** папку, а затем выберите **свойства** в контекстном меню.
    1. В **GettingStartedHost** окне для **автоматически запускаемый объект**выберите **Service.Program** (или точка входа для конкретного приложения) в списке. 
    2. В главном меню выберите **файл** > **сохранить все**.

### <a name="run-the-service-application"></a>Запустите приложение службы 

**HTTP не удалось зарегистрировать URL-адрес "http:\// +: 8000/GettingStarted/CalculatorService". Процесс не обладает правами доступа к этому пространству имен.** 

 Для правильного доступа запустите процесс размещения службы Windows Communication Foundation (WCF) с правами администратора:
- Для Visual Studio: Выберите программу Visual Studio в **запустить** меню, а затем выберите **дополнительные** > **Запуск от имени администратора** в контекстном меню.
- Для окна консоли: Выберите **командной** в **запустить** меню, а затем выберите **дополнительные** > **запуска от имени администратора** с помощью ярлыка меню.
- Для Windows Explorer: Выберите исполняемый объект, а затем выберите **Запуск от имени администратора** в контекстном меню.

### <a name="compile-the-client-application"></a>Скомпилируйте клиентское приложение

**'CalculatorClient', не содержит определение для "\<имя метода >" и метод расширения "\<имя метода >" принимающий первый аргумент типа 'CalculatorClient' может быть найден (возможно, отсутствует using директива или ссылка на сборку?)**  

Только методы, помеченные с помощью `ServiceOperationAttribute` атрибут предоставляются публично. Если опустить `ServiceOperationAttribute` атрибут из метода в `ICalculator` интерфейс, появляется это сообщение об ошибке во время компиляции.  

**Имя типа или пространства имен 'CalculatorClient' не найден (возможно, отсутствует using директива или ссылка на сборку?)**

 Эта ошибка появляется, если вы не добавите *generatedProxy.cs* (или *generatedProxy.vb*) файл в проект клиента при формировании их с помощью *Svcutil.exe* средство .  

### <a name="run-the-client-application"></a>Запуск клиентского приложения

**Необработанное исключение: System.ServiceModel.EndpointNotFoundException: Не удалось подключиться к "http:\//localhost:8000/GettingStarted/CalculatorService". Код ошибки TCP 10061: Не удалось установить соединение, так как конечный компьютер отверг.**

Эта ошибка возникает при запуске клиентского приложения без первый запуск службы. Во-первых запустите основное приложение для запуска службы и запустите клиентское приложение.

### <a name="use-the-svcutilexe-tool"></a>Используйте средство Svcutil.exe
   
**«Svcutil» не распознается как внутренняя или внешняя команда, исполняемая программа или пакетный файл.**

 *Svcutil.exe* должен находиться в системном пути. Самым простым решением является использование командной строки Visual Studio. Из **запустить** меню, выберите **Visual Studio \<версии >** каталог, а затем выберите **Командная строка разработчика для VS \<версии >**. Эта командная строка задает системный путь правильное расположение для всех средств, поставляемых в составе Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Запуск служб и клиентских приложений

**System.ServiceModel.Security.SecurityNegotiationException: Согласования безопасности SOAP с "http:\//localhost:8000/GettingStarted/CalculatorService" для целевого объекта "http:\//localhost:8000/GettingStarted/CalculatorService" не удалось**  

Эта ошибка возникает на присоединенных к домену компьютере, отсутствует подключение к сети. Подключение компьютера к сети или отключите безопасность для службы и клиента. 

Чтобы отключить безопасность:

- Для службы, замените код, создающий `WSHttpBinding` следующим кодом:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Для клиента, в файле конфигурации обновите  **\<безопасности >** элемента под  **\<привязки >** следующим образом:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>См. также  
 [Начало работы с приложениями WCF](getting-started-tutorial.md)  
 [Краткое руководство по устранению неполадок WCF](wcf-troubleshooting-quickstart.md)  
 [Устранение неполадок с установкой](troubleshooting-setup-issues.md)

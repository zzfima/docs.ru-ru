---
title: Работа с журналами приложения
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: 617b940d2cf15779ae3c10e4663b63c9771d44b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345903"
---
# <a name="working-with-application-logs-in-visual-basic"></a>Работа с журналами приложения в Visual Basic

Объекты `My.Application.Log` и `My.Log` упрощают запись сообщений и данных трассировки в журналы.

## <a name="how-messages-are-logged"></a>Как осуществляется регистрация сообщений

Сначала проверяется уровень серьезности сообщения с помощью свойства <xref:System.Diagnostics.TraceSource.Switch%2A> свойства журнала <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> . По умолчанию только сообщения с уровнем серьезности "Информация" и более высоким передаются прослушивателям трассировки, определенным в коллекции `TraceListener` журнала. Затем каждый прослушиватель сравнивает серьезность сообщения со свойством <xref:System.Diagnostics.TraceSource.Switch%2A> прослушивателя. Если уровень серьезности сообщения достаточно высокий, прослушиватель записывает сообщение.

На приведенной ниже схеме показан способ передачи сообщения, записанного методом `WriteEntry` , в методы `WriteLine` прослушивателей трассировки журнала.

![Схема, иллюстрирующая вызов My log.](./media/working-with-application-logs/my-log-call-messages.png)

Поведение журнала и прослушивателей трассировки можно изменить путем изменения файла конфигурации приложения. На приведенной ниже схеме показано соответствие между элементами журнала и файла конфигурации.

![Схема, иллюстрирующая настройку My log.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a>Куда записываются сообщения

Если сборка не имеет файла конфигурации, объекты `My.Application.Log` и `My.Log` записывают сообщения в вывод отладки приложения (с использованием класса <xref:System.Diagnostics.DefaultTraceListener> ). Кроме того, объект `My.Application.Log` записывает данные в файл журнала сборки (с использованием класса <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>), а объект `My.Log` записывает сообщения в вывод веб-страницы ASP.NET (с использованием класса <xref:System.Web.WebPageTraceListener>).

При работе с приложением в режиме отладки вывод отладки можно просматривать в окне Visual Studio **Вывод**. Чтобы открыть окно **Вывод** , выберите пункт меню **Отладка** , наведите указатель на пункт **Окна**и выберите пункт **Вывод**. В окне **Вывод** выберите значение **Отладка** в поле **Показать выходные данные из** .

По умолчанию объект `My.Application.Log` записывает сообщения в файл журнала, расположенный по пути данных приложения пользователя. Путь можно получить из свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> объекта <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> . Путь имеет следующий формат:

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

Стандартное значение для `BasePath` будет следующим.

C:\Documents and Settings\\`username`\Application Data

Значения параметров `CompanyName`, `ProductName`и `ProductVersion` берутся из сведений о сборке приложения. Имя файла журнала имеет следующий формат: *AssemblyName*.log, где *AssemblyName* — имя файла сборки без расширения. Если требуется несколько файлов журнала, например, когда исходный журнал недоступен при попытке записи в журнал, имя файла журнала имеет следующий формат: *AssemblyName*-*iteration*.log, где `iteration` — положительное целое число типа `Integer`.

Поведение по умолчанию можно переопределить путем добавления или изменения файлов конфигурации компьютера и приложения. Дополнительные сведения см. в разделе [Пошаговое руководство: Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).

## <a name="configuring-log-settings"></a>Настройка параметров журнала

Реализация объекта `Log` по умолчанию работает без файла конфигурации приложения app.config. Чтобы изменить значения по умолчанию, необходимо добавить файл конфигурации с новыми значениями параметров. Дополнительные сведения см. в разделе [Пошаговое руководство: Фильтрация выходных данных My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).

Разделы конфигурации журнала находятся в узле `<system.diagnostics>` в основном узле `<configuration>` файла app.config. Сведения журнала определены в нескольких узлах.

- Прослушиватели для объекта `Log` определены в узле `<sources>` с именем DefaultSource.

- Фильтр серьезности для объекта `Log` определен в узле `<switches>` с именем DefaultSwitch.

- Прослушиватели журнала определены в узле `<sharedListeners>` .

 Примеры узлов `<sources>`, `<switches>`и `<sharedListeners>` показаны в приведенном ниже коде.

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a>Изменение параметров журнала после развертывания

При разработке приложения его параметры конфигурации хранятся в файле app.config, как показано в приведенных выше примерах. После развертывания приложения настройку журнала можно по-прежнему выполнять с помощью файла конфигурации. В приложении Windows этот файл имеет имя *имяПриложения*.exe.config и должен находиться в той же папке, что и исполняемый файл. Для веб-приложения это файл Web.config, связанный с проектом.

Когда приложение выполняет код, который впервые создает экземпляр класса, выполняется проверка сведений об объекте в файле конфигурации. Для объекта `Log` это происходит при первом обращении к объекту `Log` . Система проверяет файл конфигурации только один раз для каждого отдельного объекта — при первом создании объекта в приложении. Таким образом, необходимо перезапустить приложение, чтобы изменения вступили в силу.

В развернутом приложении активация кода трассировки выполняется путем повторной настройки объектов переключателей до запуска приложения. Обычно это подразумевает включение и отключение объектов переключателей или изменение уровней трассировки, а затем перезапуск приложения.

## <a name="security-considerations"></a>Вопросы безопасности

При записи данных в журнал необходимо учитывать указанные ниже моменты.

- **Не допускайте утечки сведений о пользователе** . Записывайте в журнал только одобренные сведения. Например, в журнале приложения могут содержаться имена пользователей, но не их пароли.

- **Храните журнал в безопасном месте** . Любой журнал, который может содержать конфиденциальные данные, должен храниться в безопасном месте.

- **Не допускайте неправильных сведений** . В общем случае приложение должно проверять все данные, введенные пользователем, перед их использованием. Это относится и к записи данных в журнал приложения.

- **Не допускайте отказа в обслуживании** . Если приложение записывает в журнал слишком много сведений, это может привести к переполнению журнала или усложнить поиск важной информации.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Запись сведений в журнал из приложения](../../../../visual-basic/developing-apps/programming/log-info/index.md)

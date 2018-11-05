---
title: Пошаговое руководство. Использование служб клиентских приложений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
ms.openlocfilehash: d09ad4b1f518ac6f4c42dffd4b3ca17249b95700
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194323"
---
# <a name="walkthrough-using-client-application-services"></a>Пошаговое руководство. Использование служб клиентских приложений
В этой статье описывается создание приложения Windows, в котором для проверки подлинности пользователей и извлечения их ролей и параметров используются службы клиентских приложений.  
  
 В руководстве выполняются следующие задачи:  
  
-   Создание приложения Windows Forms и использование конструктора проектов Visual Studio для активации и настройки служб клиентского приложения.  
  
-   Создание простого приложения веб-служб ASP.NET для размещения служб приложений и тестирования конфигурации клиента.  
  
-   Реализация в приложении проверки подлинности с помощью форм. Сначала для тестирования службы будут использоваться жестко заданные имя пользователя и пароль. Затем вы добавите форму входа, указав ее в конфигурации приложения как поставщика учетных данных.  
  
-   Добавление функций на основе ролей, создание и отображение кнопки только для пользователей с ролью "manager".  
  
-   Доступ к веб-параметрам. Сначала в конструкторе проектов на странице **Параметры** вы загрузите веб-параметры (тестового) пользователя, прошедшего проверку подлинности. Затем с помощью конструктора Windows Forms вы привяжете текстовое поле к веб-параметру. После этого потребуется сохранить измененное значение на сервере.  
  
-   Реализация выхода. Вы добавите в форму элемент для выхода, а затем вызовете метод Logout.  
  
-   Включение автономного режима. Вы создадите флажок, с помощью которого пользователи смогут указывать состояние своего подключения. Указанное значение будет использоваться, чтобы определить, будут ли поставщики служб клиентских приложений использовать данные из локального кэша вместо доступа к своим веб-службам. При переходе приложения в режим "В сети" будет выполняться повторная проверка подлинности текущего пользователя.  
  
## <a name="prerequisites"></a>Предварительные требования  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.
  
## <a name="creating-the-client-application"></a>Создание клиентского приложения  
 В первую очередь следует создать проект Windows Forms. В этом пошаговом руководстве используется проект Windows Forms, поскольку с подобными проектами знакомо большинство разработчиков. Приведенные инструкции также актуальны для проектов Windows Presentation Foundation (WPF).  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a>Создание клиентского приложения и включение служб клиентских приложений  
  
1.  В Visual Studio выберите **"Файл" &#124; "Создать" &#124; "Проект"**.  
  
2.  В диалоговом окне **Новый проект** на панели **Типы проектов** разверните узел **Visual Basic** или **Visual C#** и выберите тип проекта **Windows**.  
  
3.  Убедитесь, что выбран пункт **.NET Framework 3.5** , а затем выберите шаблон **Приложение Windows Forms** .  
  
4.  Измените **Имя** проекта на `ClientAppServicesDemo`и нажмите кнопку **ОК**.  
  
     В Visual Studio откроется новый проект Windows Forms.  
  
5.  В меню **Проект** выберите пункт **Свойства ClientAppServicesDemo**.  
  
     Откроется конструктор проектов.  
  
6.  На вкладке **Службы** установите флажок **Включить службы клиентского приложения**.  
  
7.  Убедитесь, что выбран пункт **Использовать проверку подлинности с помощью форм** , а затем в полях **Местонахождение службы проверки подлинности**, **Местонахождение службы ролей**и **Местонахождение службы веб-параметров** введите значение `http://localhost:55555/AppServices`.  
  
8.  Для Visual Basic задайте на вкладке **Приложение** в поле **Режим проверки подлинности** значение **Определяется приложением**.  
  
 Указанные параметры будут сохранены конструктором проектов в файле app.config.  
  
 На данном этапе приложение настроено для доступа ко всем трем службам с одного узла. В следующем разделе для тестирования конфигурации клиента вы создадите узел, выступающий в качестве простого приложения веб-служб.  
  
## <a name="creating-the-application-services-host"></a>Создание узла служб приложений  
 В этом разделе вы создадите простое приложение веб-служб для доступа к пользовательским данным, хранящимся в файле локальной базы данных SQL Server Compact. Затем нужно будет заполнить базу данных при помощи [ASP.NET Web Site Administration Tool](https://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec). Выполнив простую настройку, вы сможете быстро протестировать ваше клиентское приложение. В качестве альтернативы можно настроить узел веб-служб для доступа к пользовательским данным из заполненной базы данных SQL Server или с помощью пользовательских классов <xref:System.Web.Security.MembershipProvider> и <xref:System.Web.Security.RoleProvider> . Для получения дополнительной информации см. [Creating and Configuring the Application Services Database for SQL Server](https://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2).  
  
 В следующей процедуре описывается создание и настройка веб-службы AppServices.  
  
#### <a name="to-create-and-configure-the-application-services-host"></a>Создание и настройка узла служб приложений  
  
1.  В окне **Обозреватель решений** щелкните решение ClientAppServicesDemo, а затем в меню **Файл** выберите пункты **Добавить&#124;&#124; Создать проект**.  
  
2.  В диалоговом окне **Добавление нового проекта** на панели **Типы проектов** разверните узел **Visual Basic** или **Visual C#** и выберите тип проекта **Веб**.  
  
3.  Убедитесь, что в раскрывающемся меню выше выбран пункт **.NET Framework 3.5** , а затем щелкните шаблон **Приложение веб-служб ASP.NET** .  
  
4.  Измените **Имя** проекта на `AppServices` и нажмите кнопку **ОК**.  
  
     В решение будет добавлен новый проект приложения веб-служб ASP.NET, и в редакторе появится файл Service1.asmx.vb или Service1.asmx.cs.  
  
    > [!NOTE]
    >  Этот файл не используется в данном примере. Если вы не хотите перегружать рабочую среду, ненужный файл можно удалить в окне **Обозреватель решений**.  
  
5.  В **Обозревателе решений**щелкните проект AppServices, а затем в меню **Проект** выберите пункт **Свойства AppServices**.  
  
     Откроется конструктор проектов.  
  
6.  Перейдите на вкладку **Веб** и убедитесь, что выбран пункт **Использовать Visual Studio Development Server** .  
  
7.  Выберите пункт **Указанный порт**и укажите значение `55555`, а затем в поле **Виртуальный путь** введите `/AppServices`.  
  
8.  Сохраните все файлы.  
  
9. В **Обозревателе решений**откройте файл Web.config и найдите открывающий тег `<system.web>` .  
  
10. Перед тегом `<system.web>` вставьте приведенный ниже код.  
  
     Элементы `authenticationService`, `profileService`, и `roleService` в данном коде предназначены для включения и настройки служб приложений. В целях тестирования атрибуту `requireSSL` элемента `authenticationService` присвоено значение "false". Атрибуты `readAccessProperties` и `writeAccessProperties` элемента `profileService` указывают, что свойство `WebSettingsTestText` доступно для чтения и записи.  
  
    > [!NOTE]
    >  В рабочем коде следует всегда обращаться к службе проверки подлинности с помощью протокола SSL (с использованием протокола HTTPS). Сведения о настройке SSL см. в разделе [Настройка протокола SSL (руководство пользователя IIS 6.0)](https://go.microsoft.com/fwlink/?LinkId=91844).  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. После открывающего тега `<system.web>` вставьте приведенный ниже код, который должен принадлежать элементу `<system.web>` .  
  
     Элемент `profile` предназначен для настройки одного веб-параметра `WebSettingsTestText`.  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 В следующей процедуре показано использование средства администрирования веб-сайта ASP.NET для завершения настройки службы и заполнения файла локальной базы данных. Вы добавите двух пользователей: `employee` и `manager` . Каждому будет присвоена роль с аналогичным именем. Пароли пользователей: `employee!` и `manager!` соответственно.  
  
#### <a name="to-configure-membership-and-roles"></a>Настройка членства и ролей  
  
1.  В **Обозревателе решений**щелкните проект AppServices, а затем в меню **Проект** выберите пункт **Настройка ASP.NET**.  
  
     Откроется **Средство администрирования веб-сайта ASP.NET** .  
  
2.  На вкладке **Безопасность** щелкните ссылку **Использовать мастер настройки безопасности для пошаговой установки параметров безопасности**.  
  
     Откроется **Мастер настройки безопасности** и отобразится **Экран приветствия** .  
  
3.  Нажмите кнопку **Далее**.  
  
     Отобразится страница **Выбор способа доступа** .  
  
4.  Выберите **Через Интернет**. Вместо проверки подлинности Windows в службе будет использоваться проверка подлинности с помощью форм.  
  
5.  Нажмите кнопку **Далее** дважды.  
  
     Отобразится страница **Определение ролей** .  
  
6.  Установите флажок **Включить роли для этого веб-сайта**.  
  
7.  Нажмите кнопку **Далее**. Отобразится форма **Создание новой роли** .  
  
8.  В текстовом поле **Имя новой роли** введите `manager` и нажмите кнопку **Добавить роль**.  
  
     Отобразится таблица **Существующие роли** с указанным значением.  
  
9. В текстовом поле **Имя новой роли** замените `manager` на `employee` и нажмите кнопку **Добавить роль**.  
  
     В таблице **Существующие роли** появится новое значение.  
  
10. Нажмите кнопку **Далее**.  
  
     Отобразится страница **Добавление новых пользователей** .  
  
11. В форме **Создание пользователя** укажите следующие значения.  
  
  	|||  
  	|-|-|  
  	|**Имя пользователя**|`manager`|  
  	|**Пароль**|`manager!`|  
  	|**Подтверждение пароля**|`manager!`|  
  	|**Электронная почта**|`manager@contoso.com`|  
  	|**Контрольный вопрос**|`manager`|  
  	|**Ответ на контрольный вопрос**|`manager`|  
  
12. Нажмите кнопку **Создать пользователя**.  
  
     Отобразится сообщение об успешном создании пользователя.  
  
    > [!NOTE]
    >  Поля формы **Электронная почта**, **Контрольный вопрос**и **Ответ на контрольный вопрос** обязательны для заполнения, но не используются в этом примере.  
  
13. Нажмите кнопку **Продолжить**.  
  
     Отобразится форма **Создание пользователя** .  
  
14. В форме **Создание пользователя** укажите следующие значения.  
  
  	|||  
  	|-|-|  
  	|**Имя пользователя**|`employee`|  
  	|**Пароль**|`employee!`|  
  	|**Подтверждение пароля**|`employee!`|  
  	|**Электронная почта**|`employee@contoso.com`|  
  	|**Контрольный вопрос**|`Employee`|  
  	|**Ответ на контрольный вопрос**|`employee`|  
  
15. Нажмите кнопку **Создать пользователя**.  
  
     Отобразится сообщение об успешном создании пользователя.  
  
16. Нажмите кнопку **Готово**.  
  
     Снова откроется **Средство администрирования веб-сайта** .  
  
17. Выберите пункт **Управление пользователями**.  
  
     Отобразится список пользователей.  
  
18. Щелкните **Изменить роли** в строке **employee** и выберите роль **employee** .  
  
19. Щелкните **Изменить роли** в строке **manager** и выберите роль **manager** .  
  
20. Закройте окно браузера, в котором открыто **Средство администрирования веб-сайта**.  
  
21. Если появится окно сообщения с запросом на перезагрузку измененного файла Web.config, нажмите кнопку **Да**.  
  
 Это завершит настройку веб-службы. Вы можете нажать клавишу F5, чтобы запустить клиентское приложение. При этом будет автоматически запущен **ASP.NET Development Server** . Сервер продолжит работать после выхода из приложения, но при его перезапуске будет также перезапущен. Это позволит обнаружить все изменения, внесенные в файл Web.config.  
  
 Чтобы вручную остановить сервер, щелкните правой кнопкой мыши значок ASP.NET Development Server в области уведомлений на панели задач и выберите команду **Остановить**. Иногда это может потребоваться для выполнения чистого перезапуска.  
  
## <a name="adding-forms-authentication"></a>Добавление проверки подлинности с помощью форм  
 В следующей процедуре вы добавите в главную форму код для проверки подлинности пользователей и блокирования доступа в случае ввода недействительных учетных данных. Для тестирования службы будут использоваться жестко заданные имя пользователя и пароль.  
  
#### <a name="to-validate-the-user-in-your-application-code"></a>Проверка пользователей в коде приложения  
  
1.  В окне **Обозреватель решений** для проекта ClientAppServicesDemo добавьте ссылку на сборку System.Web.  
  
2.  Щелкните файл Form1 и в главном меню Visual Studio выберите **"Вид" &#124; "Код"**.  
  
3.  В редакторе кода добавьте следующие операторы в начале файла Form1.  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]
     [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  В окне **Обозреватель решений**дважды щелкните файл Form1, чтобы отобразить конструктор.  
  
5.  В конструкторе дважды щелкните поверхность формы, чтобы создать обработчик событий <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> с названием `Form1_Load`.  
  
     Откроется редактор кода, курсор окажется в области метода `Form1_Load` .  
  
6.  Добавьте следующий код в метод `Form1_Load` .  
  
     Благодаря этому коду пользователи, не прошедшие проверку подлинности, не смогут получить доступ к приложению — приложение будет закрыто. Кроме того, можно разрешить пользователям доступ к форме в случае неудачной проверки подлинности, но блокировать при этом определенные функции. Как правило, имя пользователя и пароль не задаются жестко, как в данном примере, однако это может быть полезно в целях тестирования. В следующем разделе вы замените этот код более надежным, позволяющим отображать диалоговое окно входа и предусматривающим обработку исключений.  
  
     Обратите внимание, что метод `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> включен в [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]. Функции данного метода делегируются указанному поставщику проверки подлинности. В случае удачной проверки подлинности возвращается значение `true` . В вашем приложении не требуется прямых ссылок на поставщика проверки подлинности клиента.  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]
     [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 Теперь вы можете запустить приложение с помощью клавиши F5. Поскольку вы указали правильные имя пользователя и пароль, отобразится форма.  
  
> [!NOTE]
>  Если не удалось запустить приложение, попробуйте остановить ASP.NET Development Server. После перезапуска сервера убедитесь, что для параметра "Порт" задано значение "55555".  
  
 Чтобы отобразить сообщение об ошибке, измените параметры <xref:System.Web.Security.Membership.ValidateUser%2A> . Например, замените значение второго параметра ( `"manager!"` ) неправильным паролем (например, `"MANAGER"`).  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a>Добавление формы входа в качестве поставщика учетных данных  
 Вы можете получать учетные данные пользователей с помощью кода своего приложения и передавать их методу <xref:System.Web.Security.Membership.ValidateUser%2A> . Однако на случай, если вы решите изменить код получения учетных данных, бывает полезно держать его отдельно от остального кода приложения.  
  
 В следующей процедуре описывается настройка приложения на использование поставщика учетных данных. При вызове метода <xref:System.Web.Security.Membership.ValidateUser%2A> обоим параметрам будет передаваться значение <xref:System.String.Empty> . Пустые строки отдают методу <xref:System.Web.Security.Membership.ValidateUser%2A> команду вызова метода <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> указанного поставщика учетных данных.  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a>Настройка приложения на использование поставщика учетных данных  
  
1.  В окне **Обозреватель решений**щелкните проект ClientAppServicesDemo, а затем в меню **Проект** выберите пункт **Свойства ClientAppServicesDemo**.  
  
     Откроется конструктор проектов.  
  
2.  На вкладке **Службы** установите следующее значение для параметра **Необязательно: поставщик учетных данных** . Это значение определяет имя типа с указанием сборки.  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  В файле с текстом программы Form1 замените код метода `Form1_Load` представленным ниже.  
  
     Этот код отображает приветственное сообщение, а затем вызывает метод `ValidateUsingCredentialsProvider` , который вы добавите в следующем шаге. Если пользователь не проходит проверку подлинности, метод `ValidateUsingCredentialsProvider` возвращает значение `false` , а также выполняется возврат метода `Form1_Load` . Это позволяет предотвратить выполнение любого дополнительного кода до выхода из приложения. Приветственное сообщение позволяет понять, когда выполняется перезапуск приложения. Добавление кода перезапуска приложения описывается ниже в разделе "Реализация выхода".  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]
     [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  Добавьте приведенный ниже метод после метода `Form1_Load` .  
  
     Этот метод передает пустые строки методу <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`), благодаря которому отображается диалоговое окно входа. Если служба проверки подлинности недоступна, метод <xref:System.Web.Security.Membership.ValidateUser%2A> вызывает исключение <xref:System.Net.WebException>. В этом случае метод `ValidateUsingCredentialsProvider` отобразит предупреждающее сообщение и предложение повторить попытку в автономном режиме. Для этого требуется включить функцию **Локально сохранять хэш пароля для обеспечения входа вне сети** , как описано в разделе [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). Для новых проектов эта функция включена по умолчанию.  
  
     Если пользователь не прошел проверку подлинности, метод `ValidateUsingCredentialsProvider` отображает сообщение об ошибке и завершает работу приложения. Этот метод также возвращает результат попытки проверки подлинности.  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]
     [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a>Создание формы входа  
 Поставщик учетных данных — это класс, реализующий интерфейс <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> . Этот интерфейс содержит один метод с именем <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> , возвращающий объект <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> . В следующей процедуре описывается создание диалогового окна входа. Для отображения окна и возвращения указанных пользователем учетных данных используется метод <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> .  
  
 Для Visual Basic и C# представлены отдельные инструкции, так как в Visual Basic доступен шаблон **Форма входа**. Это позволяет сократить время и затраты на кодирование.  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a>Создание диалогового окна входа как поставщика учетных данных в Visual Basic  
  
1.  На панели **Обозреватель решений**щелкните проект ClientAppServicesDemo, а затем в меню **Проект** выберите пункт **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавление нового элемента** выберите шаблон **Форма входа** , измените **Имя** на `Login.vb`и нажмите кнопку **Добавить**.  
  
     В конструкторе Windows Forms отобразится диалоговое окно входа.  
  
3.  В конструкторе нажмите кнопку **OK** , а затем в окне **Свойства** выберите для параметра `DialogResult` значение `OK`.  
  
4.  В конструкторе добавьте в форму элемент управления `CheckBox` под текстовым полем **Пароль** .  
  
5.  В окне **Свойства** укажите для параметра **(Name)** значение `rememberMeCheckBox`, а для параметра **Text** — `&Remember me`.  
  
6.  В главном меню Visual Studio выберите **"Вид" &#124; "Код"**.  
  
7.  В редакторе кода добавьте в начало файла следующий код.  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  Измените сигнатуру класса, чтобы обеспечить реализацию интерфейса <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> .  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. Установите курсор после кода интерфейса `IClientformsAuthenticationCredentialsProvider` и нажмите клавишу ВВОД, чтобы создать метод `GetCredentials`.  
  
10. Найдите код, с помощью которого реализуется метод <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> , и замените его на приведенный ниже.  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 В следующей процедуре для C# приводится полный код создания простого диалогового окна входа. Макет этого диалогового окна достаточно приблизителен, однако главный интерес здесь представляет реализация метода <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> .  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a>Создание диалогового окна входа как поставщика учетных данных в C#  
  
1.  В окне **Обозреватель решений**щелкните проект ClientAppServicesDemo, а затем в меню **Проект** выберите пункт **Добавить класс**.  
  
2.  В диалоговом окне **Добавление нового элемента** измените **Имя** на `Login.cs`и нажмите кнопку **Добавить**.  
  
     В редакторе кода откроется файл Login.cs.  
  
3.  Замените код по умолчанию представленным ниже.  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 Теперь вы можете запустить приложение. Отобразится диалоговое окно входа. Чтобы проверить код, попробуйте вводить разные учетные данные, как действительные, так и недействительные. Доступ к форме должен открываться только при вводе действительных учетных данных. Допустимые имена пользователей — `employee` и `manager` с паролями `employee!` и `manager!` соответственно.  
  
> [!NOTE]
>  Не устанавливайте флажок **Запомнить мои данные** , так как в этом случае вы не сможете войти как другой пользователь, пока не реализуете функцию выхода, описанную далее в этом руководстве.  
  
## <a name="adding-role-based-functionality"></a>Добавление функций на основе ролей  
 В следующей процедуре вы добавите в форму кнопку, которая будет отображаться только для пользователей с ролью "manager".  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a>Изменение пользовательского интерфейса в зависимости от роли пользователя  
  
1.  В **обозревателе решений** найдите проект ClientAppServicesDemo, выберите Form1, а затем в главном меню Visual Studio выберите **"Вид" &#124; "Конструктор"**.  
  
2.  В конструкторе откройте меню **Панель элементов** и добавьте в форму элемент управления <xref:System.Windows.Forms.Button>.  
  
3.  В окне **Свойства** задайте следующие свойства кнопки.  
  
  	|Свойство.|Значение|  
  	|--------------|-----------|  
  	|**(Name)**|managerOnlyButton|  
  	|**Text**|&Manager task|  
  	|**Показывается**|`False`|  
  
4.  В редакторе кода формы Form1 добавьте в конце метода `Form1_Load` приведенный ниже код.  
  
     Этот код вызывает метод `DisplayButtonForManagerRole` , который будет добавлен в следующем шаге.  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]
     [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  В конце класса Form1 добавьте приведенный ниже метод.  
  
     Этот метод вызывает метод <xref:System.Security.Principal.IPrincipal.IsInRole%2A> интерфейса <xref:System.Security.Principal.IPrincipal>, возвращенного свойством <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> (`static`). Для приложений, настроенных на использование служб клиентских приложений, это свойство возвращает класс <xref:System.Web.ClientServices.ClientRolePrincipal>. Поскольку этот класс реализует интерфейс <xref:System.Security.Principal.IPrincipal> , необязательно явно ссылаться на него.  
  
     Если пользователю назначена роль "manager", метод `DisplayButtonForManagerRole` присваивает свойству <xref:System.Windows.Forms.Control.Visible%2A> кнопки `managerOnlyButton` значение `true`. При вызове исключения <xref:System.Net.WebException> этот метод также отображает сообщение об ошибке, означающее, что служба ролей недоступна.  
  
    > [!NOTE]
    >  При истечении допустимого времени в системе метод <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> всегда возвращает значение `false` . Этого не происходит, если приложение вызывает метод <xref:System.Security.Principal.IPrincipal.IsInRole%2A> один раз вскоре после проверки подлинности, как показано в примере кода, который используется в этом руководстве. Если необходимо, чтобы приложение извлекало роли пользователей в другое время, вы можете добавить код для повторной проверки пользователей, чье допустимое время в системе истекло. Если всем допустимым пользователям назначены роли, вы можете выявлять истечение допустимого времени, вызывая метод <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> . Если роли не возвращаются, значит время истекло. Пример реализации этой возможности — метод <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> . Данная функция необходима лишь в случае, если в параметрах приложения вы выбрали пункт **Требовать, чтобы пользователи повторяли вход, если у файла cookie сервера истек срок действия** . Дополнительные сведения см. в разделе [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]
     [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 В случае успешной проверки подлинности поставщик проверки подлинности клиента назначает свойство <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> экземпляру класса <xref:System.Web.ClientServices.ClientRolePrincipal> . Этот класс реализует метод <xref:System.Security.Principal.IPrincipal.IsInRole%2A> — функции делегируются заданному поставщику ролей. Как и ранее, в коде приложения не требуются прямые ссылки на поставщика услуг.  
  
 Теперь вы можете запустить приложение и войти в систему с именем пользователя "employee", чтобы убедиться, что кнопка не отображается. После этого попробуйте войти с именем "manager" — кнопка должна отображаться.  
  
## <a name="accessing-web-settings"></a>Доступ к веб-параметрам  
 В следующей процедуре вы добавите на форму текстовое поле и привяжете его к веб-параметрам. Как и в ранее описанном коде, с помощью которого были реализованы проверка подлинности и доступ к функциям в зависимости от ролей, в коде ваших параметров не требуется прямых ссылок на поставщика параметров. Вместо этого используется строго типизированный класс `Settings` (`Properties.Settings.Default` в C# и `My.Settings` в Visual Basic), созданный Visual Studio для вашего проекта.  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a>Использование веб-параметров в пользовательском интерфейсе  
  
1.  Проверьте область уведомлений на панели задач и убедитесь, что **Сервер веб-разработки ASP.NET** запущен. Если вы останавливали сервер, перезапустите приложение и закройте диалоговое окно входа. Сервер будет запущен автоматически.  
  
2.  В окне **Обозреватель решений**щелкните проект ClientAppServicesDemo, а затем в меню **Проект** выберите пункт **Свойства ClientAppServicesDemo**.  
  
     Откроется конструктор проектов.  
  
3.  На вкладке **Параметры** выберите команду **Загрузить веб-параметры**.  
  
     Появится диалоговое окно **Имя для входа** .  
  
4.  Введите учетные данные для пользователя "employee" или "manager" и нажмите кнопку **Войти**. Получить доступ веб-параметрам, которые будут использоваться в дальнейшем, могут только пользователи, прошедшие проверку подлинности. Если нажать кнопку **Пропустить вход** , параметры не будут загружены.  
  
     В конструкторе появится параметр `WebSettingsTestText` со значением по умолчанию `DefaultText`. В вашем проекте также будет создан класс `Settings`, содержащий свойство `WebSettingsTestText`.  
  
5.  В **обозревателе решений** найдите проект ClientAppServicesDemo, выберите Form1, а затем в главном меню Visual Studio выберите **"Вид" &#124; "Конструктор"**.  
  
6.  В конструкторе добавьте на форму элемент управления <xref:System.Windows.Forms.TextBox>.  
  
7.  В окне **Свойства** укажите для параметра **(Name)** значение `webSettingsTestTextBox`.  
  
8.  В редакторе кода добавьте в конце метода `Form1_Load` приведенный ниже код.  
  
     Этот код вызывает метод `BindWebSettingsTestTextBox` , который будет добавлен в следующем шаге.  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]
     [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. В конце класса Form1 добавьте приведенный ниже метод.  
  
     Этот метод привязывает свойство <xref:System.Windows.Forms.TextBox.Text%2A> метода `webSettingsTestTextBox` к свойству `WebSettingsTestText` класса `Settings` , создание которого описывалось ранее в этой процедуре. При вызове исключения <xref:System.Net.WebException> этот метод также отображает сообщение об ошибке, означающее, что служба веб-параметров недоступна.  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]
     [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  Привязка данных обычно используется для автоматического двустороннего взаимодействия между элементом управления и веб-параметром. Однако вы также можете использовать веб-параметры напрямую, как показано в следующем примере:  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]
     [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. В конструкторе выберите форму, а затем в окне **Свойства** нажмите кнопку **События** .  
  
11. Выберите событие <xref:System.Windows.Forms.Form.FormClosing> и нажмите клавишу ВВОД, чтобы создать обработчик события.  
  
12. Замените созданный метод приведенным ниже кодом.  
  
     Обработчик события <xref:System.Windows.Forms.Form.FormClosing> вызывает метод `SaveSettings` , также используемый функцией выхода, которая будет добавлена в следующем разделе. Метод `SaveSettings` сначала проверяет, не вышел ли пользователь из системы. Это достигается путем проверки свойства <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> <xref:System.Security.Principal.IIdentity>, возвращенного текущим субъектом. Текущий субъект извлекается с помощью свойства <xref:System.Threading.Thread.CurrentPrincipal%2A> (`static`). Если пользователь прошел проверку подлинности служб клиентских приложений, используется проверка подлинности типа "ClientForms". Метод `SaveSettings` не может просто проверить свойство <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> , поскольку после выхода у пользователя может иметься допустимое удостоверение Windows.  
  
     Если пользователь не выходил из системы, метод `SaveSettings` вызывает метод <xref:System.Configuration.ApplicationSettingsBase.Save%2A> , принадлежащий классу `Settings` . Создание этого класса описывалось выше. При истечении срока действия файла cookie проверки подлинности этот метод может вызвать исключение <xref:System.Net.WebException> . Это возможно лишь в случае, если в параметрах приложения вы выбрали пункт **Требовать, чтобы пользователи повторяли вход, если у файла cookie сервера истек срок действия** . Дополнительные сведения см. в разделе [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md). При истечении срока действия файлов cookie метод `SaveSettings` вызывает метод <xref:System.Web.Security.Membership.ValidateUser%2A> для отображения диалогового окна входа в систему. В случае успешного входа пользователя метод `SaveSettings` вызывает сам себя, предпринимая попытку повторного сохранения параметров.  
  
     Как и в предшествующем коде, если удаленная служба недоступна, метод `SaveSettings` отображает сообщение об ошибке. Если поставщик параметров не может получить доступ к удаленной службе, параметры сохраняются в локальном кэше и перезагружаются при повторном запуске приложения.  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]
     [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. В конце класса Form1 добавьте приведенный ниже метод.  
  
     Этот код обрабатывает событие <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> и отображает предупреждение, если какие-либо параметры не удалось сохранить. Если служба параметров недоступна или истек срок действия файла cookie проверки подлинности, событие <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> не происходит. Событие <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> происходит, например, если пользователь уже вышел из системы. Вы можете проверить этот обработчик событий, непосредственно перед вызовом метода `SaveSettings` добавив в метод <xref:System.Configuration.ApplicationSettingsBase.Save%2A> код выхода. Код выхода, который можно при этом использовать, описывается в следующем разделе.  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]
     [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. При использовании C# добавьте в конце метода `Form1_Load` следующий код. Это позволит связать добавленный в последнем шаге метод с событием <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> .  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 Чтобы проверить приложение на данном этапе, запустите его несколько раз, пробуя входить в систему с именем "employee" и "manager" и вводя в текстовое поле разные значения. Для каждого пользователя эти значения будут сохраняться между сеансами.  
  
## <a name="implementing-logout"></a>Реализация выхода  
 Если при входе установить флажок **Запомнить мои данные** , при следующих запусках приложения проверка подлинности будет выполняться автоматически. Автоматическая проверка подлинности продолжит выполняться, пока приложение находится в автономном режиме или до истечения срока действия файла cookie проверки подлинности. Однако иногда доступ к приложению может потребоваться нескольким пользователям, или же какой-либо пользователь может войти в систему с другими учетными данными. Для таких случаев необходимо реализовать функцию выхода с помощью процедуры, описанной далее.  
  
#### <a name="to-implement-logout-functionality"></a>Реализация функции выхода  
  
1.  В конструкторе откройте меню **Панель элементов** и добавьте на форму Form1 элемент управления <xref:System.Windows.Forms.Button>.  
  
2.  В окне **Свойства** укажите для параметра **(Name)** значение `logoutButton`, а для параметра **Text** — **&Выйти**.  
  
3.  Дважды щелкните кнопку `logoutButton`, чтобы создать обработчик события <xref:System.Windows.Forms.Control.Click>.  
  
     Откроется редактор кода, курсор окажется в области метода `logoutButton_Click` .  
  
4.  Замените созданный метод `logoutButton_Click` приведенным ниже кодом.  
  
     Этот обработчик событий сначала вызывает метод `SaveSettings` , добавление которого описывается в прошлом разделе. Затем обработчик событий вызывает метод <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> . Если служба проверки подлинности недоступна, метод <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> вызывает исключение <xref:System.Net.WebException>. В этом случае метод `logoutButton_Click` отображает предупреждающее сообщение и временно переводит приложение в автономный режим, чтобы пользователь вышел из системы. Автономный режим описывается в следующем разделе.  
  
     При выходе удаляется локальный файл cookie проверки подлинности, поэтому при перезапуске приложения потребуется выполнить повторный вход в систему. После выхода обработчик события перезапускает приложение. При перезапуске программы отображается приветственное сообщение, а затем — диалоговое окно входа. Приветственное сообщение позволяет понять, что приложение было перезапущено. Это позволяет избежать путаницы в случаях, когда пользователю требуется войти в систему для сохранения параметров, а затем снова выполнить вход из-за перезапуска приложения.  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]
     [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 Чтобы проверить функцию выхода, запустите приложение и установите в диалоговом окне входа флажок **Запомнить мои данные** . После этого закройте и заново откройте приложение, чтобы проверить, что при входе больше не требуется вводить учетные данные. Наконец, нажмите кнопку "Выход", чтобы перезапустить приложение.  
  
## <a name="enabling-offline-mode"></a>Включение автономного режима  
 В следующей процедуре описывается добавление на форму флажка перехода в автономный режим. Приложение переводится в автономный режим при присвоении свойству <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> (`static`) значения `true`. Автономное состояние хранится на локальном жестком диске в расположении, заданном свойством <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>. Это означает, для каждого пользователя и приложения автономное состояние хранится отдельно.  
  
 В автономном режиме вместо попыток прямого доступа к службам все запросы служб клиентских приложений извлекают данные из локального кэша. По умолчанию локальные данные содержат зашифрованный пароль пользователя. Это позволят пользователю входить в систему, когда приложение находится в автономном режиме. Для получения дополнительной информации см. [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
#### <a name="to-enable-offline-mode-in-your-application"></a>Включение автономного режима в приложении  
  
1.  В **обозревателе решений** найдите проект ClientAppServicesDemo, выберите Form1, а затем в главном меню Visual Studio выберите **"Вид" &#124; "Конструктор"**.  
  
2.  В конструкторе добавьте на форму элемент управления <xref:System.Windows.Forms.CheckBox>.  
  
3.  В окне **Свойства** укажите для параметра **(Name)** значение `workOfflineCheckBox`, а для параметра **Text** — **&Автономная работа**.  
  
4.  В окне **Свойства** нажмите кнопку **События** .  
  
5.  Выберите событие <xref:System.Windows.Forms.CheckBox.CheckedChanged> и нажмите клавишу ВВОД, чтобы создать обработчик события.  
  
6.  Замените созданный метод приведенным ниже кодом.  
  
     Этот код обновляет значение <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> и автоматически выполняет проверку подлинности пользователя при подключении к Интернету. В методе <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> используются кэшированные учетные данные, поэтому пользователю не требуется явным образом входить в систему. Если служба проверки подлинности недоступна, отобразится предупреждающее сообщение и приложение останется в автономном режиме.  
  
    > [!NOTE]
    >  Метод <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> предназначен исключительно для удобства. Поскольку у него отсутствуют возвращаемые значения, с его помощью нельзя выявлять ошибки при повторных проверках подлинности. Ошибка проверки подлинности может возникнуть, например, при изменении учетных данных пользователя на сервере. В этом случае вы можете использовать код, с помощью которого после ошибок вызова служб будет выполняться явная проверка подлинности пользователей. Дополнительные сведения см. в разделе "Доступ к веб-параметрам" в данном руководстве.  
  
     После повторной проверки подлинности этот код вызывает метод `SaveSettings` , добавление которого рассматривается выше, чтобы сохранить все изменения локальных веб-параметров. Затем с помощью этого кода на сервере извлекаются все новые значения путем вызова метода <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> класса проекта `Settings` (`Properties.Settings.Default` в C# и `My.Settings` в Visual Basic).  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]
     [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  Чтобы флажок точно соответствовал текущему состоянию подключения, добавьте в конце метода `Form1_Load` следующий код.  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]
     [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 На этом создание примера приложения завершено. Чтобы проверить функции программы в автономном режиме, запустите приложение, войдите в систему, используя имя "employee" или "manager", а затем установите флажок **Автономная работа**. Измените значение в текстовом поле и закройте приложение. Перезапустите программу. Перед повторным входом щелкните правой кнопкой мыши значок сервера разработки ASP.NET в области уведомлений на панели задач и выберите команду **Остановить**. После этого войдите в систему обычным образом. Даже если сервер остановлен, вход должен пройти успешно. Измените значение в текстовом поле и перезапустите приложение, чтобы проверить, сохранились ли изменения.  
  
## <a name="summary"></a>Сводка  
 В этом пошаговом руководстве вы узнали, как включить и использовать службы клиентских приложений в программе Windows Forms. После настройки тестового сервера вы добавили в свое приложение код для проверки подлинности пользователей и для извлечения с сервера пользовательских ролей и параметров приложения. Вы также узнали, как включить автономный режим, чтобы вместо удаленных служб приложение использовало данные из локального кэша, если установить подключение невозможно.  
  
## <a name="next-steps"></a>Следующие шаги  
 В реальности удаленный сервер с используемыми данными множества пользователей может быть не всегда доступен или неожиданно прекратить работу. Для создания надежных приложений необходимо предусмотреть ситуации, когда служба недоступна. В этом пошаговом руководстве приводятся блоки try/catch для перехвата исключений <xref:System.Net.WebException> и отображения сообщений об ошибке, если служба недоступна. В рабочем коде на этот случай может потребоваться возможность перехода в автономный режим, выхода из приложения или блокирования определенных функций.  
  
 Чтобы повысить безопасность ваших приложений, тщательно тестируйте программы и серверы перед развертыванием.  
  
## <a name="see-also"></a>См. также  
 [Службы клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Общие сведения о службах клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Средство администрирования веб-сайта ASP.NET](https://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)  
 [Создание и настройка базы данных служб приложений для SQL Server](https://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)  
 [Пошаговое руководство. Использование служб приложений ASP.NET](https://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)

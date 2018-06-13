---
title: Практическое руководство. Реализация входа пользователя с помощью служб клиентских приложений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
ms.openlocfilehash: 1b1c5bebb5bd94f0a56dc6da303ef2503ab6dd4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743814"
---
# <a name="how-to-implement-user-login-with-client-application-services"></a>Практическое руководство. Реализация входа пользователя с помощью служб клиентских приложений
Службы клиентских приложений можно использовать для проверки подлинности пользователей с помощью существующей службы профилей [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]. Сведения о настройке службы профилей [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] см. в разделе [Использование проверки подлинности с помощью форм в Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).  
  
 В приведенных ниже процедурах описываются способы проверки пользователей с помощью службы проверки подлинности в случае, если приложение настроено на использование одного из поставщиков служб проверки подлинности клиента. Дополнительные сведения см. в разделе [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Все проверки обычно выполняются с помощью метода <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`). Этот метод управляет взаимодействием со службой проверки подлинности посредством настроенного поставщика проверки подлинности. Дополнительные сведения см. в разделе [Общие сведения о службах клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
 Для использования процедур проверки подлинности с помощью форм требуется доступ к запущенной службе проверки подлинности [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]. Инструкции по сквозному тестированию возможностей служб клиентских приложений см. в разделе [Пошаговое руководство. Использование служб клиентских приложений](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a>Проверка подлинности пользователя с помощью форм (с использованием поставщика учетных данных для членства)  
  
1.  Реализовать интерфейс <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>. В следующем примере кода демонстрируется реализация класса диалогового окна входа <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType>, полученного из класса <xref:System.Windows.Forms.Form?displayProperty=nameWithType>. В этом диалоговом окне присутствуют текстовые поля для ввода имени пользователя и пароля, а также флажок "Запомнить мои данные". Когда поставщик проверки подлинности клиента вызывает метод <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>, отображается форма. Когда пользователь вводит информацию в диалоговом окне входа и нажимает кнопку "ОК", указанные значения возвращаются в новом объекте <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  Вызовите метод <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`) и используйте пустые строки в качестве значений параметров. Если указать пустые строки, этот метод во внутреннем режиме вызовет метод <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> для поставщика учетных данных, указанного в вашем приложении. В следующем примере кода этот метод используется для ограничения доступа ко всему приложению Windows Forms. Вы можете добавить этот код в обработчик события <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a>Проверка подлинности пользователя с помощью форм (без использования поставщика учетных данных для членства)  
  
-   Вызовите метод <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`) и введите имя пользователя и пароль, полученные из данных пользователя.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a>Проверка подлинности пользователя с помощью аутентификации Windows  
  
-   Вызовите метод <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`) и используйте пустые строки в качестве значений параметров. При вызове этого метода всегда возвращается значение `true`, а также выполняется добавление файла cookie в кэш пользователя, в котором хранится удостоверение Windows.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В примере кода, приведенном в этом разделе, демонстрируется простейшее использование проверки подлинности в клиентском приложении Windows. Тем не менее при вызове метода <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> (`static`) с проверкой подлинности на основе служб клиентских приложений и форм ваш код может вызвать исключение <xref:System.Net.WebException>. Это будет означать, что служба проверки подлинности недоступна. Пример обработки подобных исключений см. в разделе [Пошаговое руководство. Использование служб клиентских приложений](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
## <a name="see-also"></a>См. также  
 [Службы клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Общие сведения о службах клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Пошаговое руководство. Использование служб клиентских приложений](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Использование проверки подлинности с помощью форм в Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)

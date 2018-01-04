---
title: "Практическое руководство. Создание службы программным способом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a>Практическое руководство. Создание службы программным способом
Если вы решили не использовать шаблон проекта службы Windows, можно написать собственные службы, задав порядок наследования и другие элементы инфраструктуры. При создании службы программными средствами, необходимо выполнить несколько шагов, которые шаблон, в противном случае будет обрабатываться автоматически:  
  
-   Класс службы необходимо настроить для наследования от <xref:System.ServiceProcess.ServiceBase> класса.  
  
-   Необходимо создать `Main` проект службы, который определяет запуск служб и вызывает метод <xref:System.ServiceProcess.ServiceBase.Run%2A> их метод.  
  
-   Необходимо переопределить <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> процедуры и заполните поля на любой код, необходимо их запуска.  
  
### <a name="to-write-a-service-programmatically"></a>Чтобы создать службу программными средствами  
  
1.  Создайте пустой проект и ссылку на необходимые пространства имен, выполните следующие действия:  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки** и выберите команду **добавить ссылку**.  
  
    2.  На **.NET Framework** перейдите к **System.dll** и нажмите кнопку **выберите**.  
  
    3.  Перейдите к пункту **System.ServiceProcess.dll** и нажмите кнопку **выберите**.  
  
    4.  Нажмите кнопку **ОК**.  
  
2.  Добавьте класс и настройте его для наследования от <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Добавьте следующий код, чтобы настроить класс службы.  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Создание `Main` классе, метод и использовать его для определения службы, будет содержать класс; `userService1` имя класса:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Переопределить <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и определить, какой-либо обработки, будет выполняться при запуске службы.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Переопределите все прочие методы, необходимые для определения пользовательской обработки для и написать код, чтобы определить действия, которые следует предпринять службы в каждом случае.  
  
7.  Добавить установщики, необходимые для приложения службы. Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Постройте проект, выбрав **построить решение** из **построения** меню.  
  
    > [!NOTE]
    >  Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.  
  
9. Создайте проект установки и настраиваемых действий для установки службы. Пример см. в разделе [Пошаговое руководство: Создание приложения службы Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Установите службу. Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Практическое руководство. Запись сведений о службах в журнал](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

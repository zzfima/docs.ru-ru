---
title: "How to: Write Services Programmatically | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "services, creating"
  - "Windows Service applications, creating"
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 21
---
# How to: Write Services Programmatically
Если шаблон проекта службы Windows не используется, то для создания службы необходимо вручную определить порядок наследования и другие элементы инфраструктуры.  При создании службы программными средствами необходимо выполнять ряд действий, которые в шаблоне выполняются автоматически:  
  
-   Необходимо сделать класс службы наследником класса <xref:System.ServiceProcess.ServiceBase>.  
  
-   В проекте службы необходимо создать метод `Main`, определяющий службы, которые должны запускаться, и вызывающий их метод <xref:System.ServiceProcess.ServiceBase.Run%2A>.  
  
-   Необходимо переопределить процедуры <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>, поместив в них код, который они должны выполнять.  
  
### Чтобы создать службу программными средствами, выполните следующие действия:  
  
1.  Создайте пустой проект и ссылку на необходимые пространства имен следующим образом:  
  
    1.  В **обозревателе решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите команду **Добавить ссылку**.  
  
    2.  На вкладке **.NET Framework** найдите **System.dll** и нажмите кнопку **Выбрать**.  
  
    3.  Перейдите к **System.ServiceProcess.dll** и снова нажмите кнопку **Выбрать**.  
  
    4.  Нажмите кнопку **ОК**.  
  
2.  Добавьте класс, сделав его наследником класса <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Чтобы настроить класс службы, добавьте следующий код:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Создайте в классе метод `Main` и используйте его для определения службы, которую будет содержать класс; имя класса — `userService1`:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и поместите в него код для выполнения действий, необходимых при запуске службы:  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  При необходимости переопределите другие методы и поместите в них код, определяющий действия службы в каждом конкретном случае.  
  
7.  Добавить установщики, необходимые для приложения службы.  Для получения дополнительной информации см. [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Постройте проект, выбрав команду **Построить решение** в меню **Построение**.  
  
    > [!NOTE]
    >  Не следует нажимать кнопку F5 для запуска проекта — таким способом проект службы запустить невозможно.  
  
9. Создайте проект установки, а также настраиваемые действия, необходимые для установки службы.  Пример см. в разделе [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Установите службу.  Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
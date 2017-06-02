---
title: "Service Application Programming Architecture | Microsoft Docs"
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
  - "ServiceController components, programming architecture"
  - "ServiceBase class, service states"
  - "Windows Service applications, code model"
  - "services, programming architecture"
  - "ServiceController class"
  - "services, states"
  - "ServiceProcessInstaller class, service application code model"
  - "Windows Service applications, states"
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# Service Application Programming Architecture
Основой приложений служб Windows являются классы, наследующие от класса <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName>.  Чтобы определить поведение служб, необходимо переопределять методы этих классов, реализуя в них требуемые функциональные возможности.  
  
 Основные классы, используемые при создании службы:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName> — при создании службы и разработке кода, отвечающего за функциональные возможности службы, в наследуемом классе необходимо переопределить методы класса <xref:System.ServiceProcess.ServiceBase>;  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=fullName> и <xref:System.ServiceProcess.ServiceInstaller?displayProperty=fullName> — эти классы используются для установки и удаления службы.  
  
 Кроме того, для управления службой может использоваться класс <xref:System.ServiceProcess.ServiceController>.  Этот класс не используется при создании службы, однако с его помощью можно осуществлять запуск и остановку службы, передавать ей команды и возвращать последовательности перечислений.  
  
## Определение поведения службы  
 Чтобы задать действия, выполняемые при изменении состояния службы в диспетчере управления службами, в классе службы необходимо переопределить базовые функции класса, отвечающие за эти действия.  Для задания поведения службы можно переопределить перечисленные ниже методы класса <xref:System.ServiceProcess.ServiceBase>.  
  
|Метод|Цель переопределения|  
|-----------|--------------------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Указание действий, которые должны быть выполнены при начале работы службы.  В этой процедуре должен содержаться код, выполняющий требуемые действия.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Указание действий, которые должны быть выполнены при приостановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Указание действий, которые должны быть выполнены при остановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Указание действий, которые должны быть выполнены при возобновлении работы службы после приостановки.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Указание действий, которые должны быть выполнены непосредственно перед завершением работы системы, если служба в это время запущена.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Указание действий, которые должны быть выполнены службой при получении настраиваемой команды.  Дополнительные сведения о настраиваемых командах см. в библиотеке MSDN.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Указание действий службы при возникновении события подсистемы управления питанием \(например, сигнала о низком уровне зарядки аккумуляторов или приостановка системы\).|  
  
> [!NOTE]
>  Эти методы соответствуют состояниям, через которые проходит служба в течение своего жизненного цикла.  Например, служба не будет реагировать на команду <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, если предварительно не был вызван метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  
  
 Ниже перечислено еще несколько полезных свойств и методов.  К ним относятся:  
  
-   Метод <xref:System.ServiceProcess.ServiceBase.Run%2A> класса <xref:System.ServiceProcess.ServiceBase>.  Это главная точка входа службы.  При создании служб с использованием шаблона приложения службы Windows код, запускающий службу, помещается в метод приложения `Main`.  Этот код может выглядеть следующим образом:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  В этих примерах используется массив типа <xref:System.ServiceProcess.ServiceBase>, в который могут быть добавлены все службы, содержащиеся в приложении. В дальнейшем эти службы могут быть запущены одновременно.  При создании единичной службы можно не использовать массив, а объявить новый объект, наследующий от <xref:System.ServiceProcess.ServiceBase>, и запустить его.  Пример см. в разделе [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Наборы свойств класса <xref:System.ServiceProcess.ServiceBase>.  Они определяют, какие методы службы можно вызывать.  Например, если для свойства <xref:System.ServiceProcess.ServiceBase.CanStop%2A> задано значение `true`, можно вызывать метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  Если для свойства <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> задано значение `true`, могут вызываться методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A> и <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>.  При задании для какого\-либо из этих свойств значения `true` необходимо переопределить и реализовать соответствующие методы.  
  
    > [!NOTE]
    >  Минимально функциональная служба должна переопределять по крайней мере методы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
 Для взаимодействия с существующими службами и управления их поведением можно использовать компонент <xref:System.ServiceProcess.ServiceController>.  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)
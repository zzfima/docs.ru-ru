---
title: "Базовый жизненный цикл программирования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "создание служб [WCF]"
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Базовый жизненный цикл программирования
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] позволяет приложениям обмениваться информацией не только в пределах одного компьютера, но и через Интернет, даже если они выполняются на различных платформах.В этом разделе приводятся задачи, которые необходимо выполнить при создании приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Пример образца работающего приложения см. в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## Основные задачи  
 Необходимо выполнить следующие основные задачи в указанном порядке:  
  
1.  Определите контракт службы.В контракте службы указывается ее сигнатура, отправляемые и получаемые ей данные и прочие данные, требуемые контрактом.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Создание контрактов служб](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Реализуйте контракт.Для реализации контракта службы создайте класс, который реализует этот контракт, и укажите пользовательские режимы работы, которые должна иметь среда выполнения.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Реализация контрактов служб](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Настройте службу, указав конечные точки и определив прочие сведения о режимах работы.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Настройка служб](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Разместите службу.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Размещение служб](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Создайте клиентское приложение.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Построение клиентов](../../../docs/framework/wcf/building-clients.md).  
  
 Несмотря на то что подразделы этого раздела приведены именно в таком порядке, некоторые сценарии не начинаются с самого начала.Например, если требуется создать клиент для существующей службы, следует начать с шага 5.При создании службы, которая будет использоваться другими службами, можно пропустить шаг 5.  
  
 Изучив принципы разработки контрактов служб, также можно ознакомиться с разделом [Введение в расширяемость](../../../docs/framework/wcf/introduction-to-extensibility.md).В случае затруднений при реализации службы см. раздел [Примеры устранения неполадок WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md): возможно, другие разработчики уже сталкивались с такими же или похожими проблемами.  
  
## См. также  
 [Реализация контрактов служб](../../../docs/framework/wcf/implementing-service-contracts.md)
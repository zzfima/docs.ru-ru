---
title: "Поддержка запросов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Поддержка запросов
Хранилище экземпляров рабочих процессов SQL записывает набор известных свойств в хранилище.Пользователи могут выполнить запрос экземпляров на основе этих свойств.В следующем списке приведены некоторые из этих известных свойств.  
  
-   **Имя узла.** Имя веб\-узла, содержащего службу.  
  
-   **Относительный путь приложения.** Путь приложения относительно веб\-узла.  
  
-   **Относительный путь службы.** Путь службы относительно приложения.  
  
-   **Имя службы.** Имя службы.  
  
-   **Пространство имен службы.** Имя пространства имен, которое использует служба.  
  
-   **Текущий компьютер.**  
  
-   **Последний компьютер**.Компьютер, на котором экземпляр службы рабочего процесса был запущен последний раз.  
  
> [!NOTE]
>  Для резидентных сценариев, использующих узел службы рабочего процесса, заполняются только последние четыре свойства.Для сценариев приложения рабочего процесса заполняется только последнее свойство.  
  
 Среда выполнения рабочего процесса предоставляет значения для первых трех свойств.Узел службы рабочего процесса предоставляет значения для свойства **Причина приостановки**.Само хранилище экземпляров рабочих процессов SQL предоставляет значения для свойства **Последний обновленный компьютер**.  
  
 Функция хранилища экземпляров рабочих процессов SQL также позволяет указать пользовательские свойства, значения которых требуется сохранять в базе данных сохраняемости и которые будут в дальнейшем использованы в запросах.Дополнительные сведения о пользовательских повышениях см. в разделе [Расширяемость хранилища](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
## Представления  
 Хранилище экземпляров содержит следующие представления.Дополнительные сведения см. в разделе [Схема базы данных постоянного хранения](../../../docs/framework/windows-workflow-foundation//persistence-database-schema.md).  
  
### Представление экземпляров  
 Представление экземпляров содержит следующие поля:  
  
1.  **Id**  
  
2.  **PendingTimer**  
  
3.  **CreationTime**  
  
4.  **LastUpdatedTime**  
  
5.  **ServiceDeploymentId**  
  
6.  **SuspensionExceptionName**  
  
7.  **SuspensionReason**  
  
8.  **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### Представление ServiceDeployments  
 Представление ServiceDeployments содержит следующие поля:  
  
1.  **SiteName**  
  
2.  **RelativeServicePath**  
  
3.  **RelativeApplicationPath**  
  
4.  **ServiceName**  
  
5.  **ServiceNamespace**  
  
### Представление InstancePromotedProperties  
 Представление InstancePromotedProperties содержит следующие поля.Дополнительные сведения о свойствах повышенного уровня см. в разделе [Расширяемость хранилища](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
1.  **InstanceId**  
  
2.  **EncodingOption**  
  
3.  **PromotionName**  
  
4.  **Value\#** \(ряд полей от **Value1** до **Value64**\).
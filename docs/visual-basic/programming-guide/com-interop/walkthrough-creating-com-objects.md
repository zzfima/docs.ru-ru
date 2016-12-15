---
title: "Пошаговое руководство. Создание объектов COM с помощью Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM-взаимодействие, создание COM-объектов"
  - "COM-взаимодействие, пошаговые руководства"
  - "COM-объекты, создание"
  - "COM-объекты, пошаговые руководства"
  - "создание объектов, COM-объекты"
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Создание объектов COM с помощью Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При создании новых приложений или компонентов рекомендуется создание сборок .NET Framework.  Однако [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] также облегчает предоставление компонента .NET Framework для COM.  Это позволяет создавать новые компоненты для более ранних версий приложения, которые требуют компоненты COM.  В этом руководстве демонстрируется использование [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для представления объектов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] как объектов COM, с использованием и без использования COM\-класса.  
  
 Простейший способ представления в качестве объекта COM — использование шаблона COM\-класса.  Шаблон COM\-класса создает новый класс, а затем настраивает проект для создания класса и уровня управляемого взаимодействия, как объекта COM, и регистрирует его в операционной системе.  
  
> [!NOTE]
>  Хотя можно представить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], как объект COM для использования в неуправляемом коде, но он не будет объектом COM и его нельзя будет использовать [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Дополнительные сведения см. в разделе [COM\-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Создание COM\-объекта при помощи шаблона COM\-класса  
  
1.  Откройте новый проект приложения Windows в меню **File**, щелкнув **New Project**.  
  
2.  В диалоговом окне **New Project** под полем **Project Types** проверьте, что установлен флажок Windows.  Выберите **Class Library** из **Templates** и затем нажмите **OK**.  Появится новый проект.  
  
3.  Выберите **Add New Item** в меню **Project**.  Откроется диалоговое окно **Добавление нового элемента**.  
  
4.  Выберите **Класс COM** из списка **Шаблоны**, а затем нажмите **Добавить**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] добавит новый класс и настроит новый проект на COM\-взаимодействие.  
  
5.  Добавьте код свойств, методов и событий в COM\-класс.  
  
6.  В меню **Построение** выберите пункт **Построить ClassLibrary1**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполнит построение сборки и зарегистрирует объект COM в операционной системе.  
  
## Создание объектов COM без шаблона COM\-класса  
 COM\-класс можно создать вручную, не используя шаблон COM\-класса.  Эта процедура может быть полезна при работе в командной строке или если вы хотите более полно контролировать определение объектов COM.  
  
#### Настройка проекта для создания объекта COM  
  
1.  Откройте новый проект приложения Windows в меню **File**, щелкнув **New Project**.  
  
2.  В диалоговом окне **New Project** под полем **Project Types** проверьте, что установлен флажок Windows.  Выберите **Class Library** из **Templates** и затем нажмите **OK**.  Появится новый проект.  
  
3.  В **обозревателе решений** щелкните правой кнопкой мыши на проект и выберите пункт **Свойства**.  Появится **Project Designer**.  
  
4.  Перейдите на вкладку **Compile**.  
  
5.  Выберите флажок **Register for COM Interop**.  
  
#### Настройка кода класса для создания объекта COM  
  
1.  В **Solution Explorer** дважды щелкните **Class1.vb** для просмотра его кода.  
  
2.  Переименуйте класс на `ComClass1`.  
  
3.  Добавьте следующие константы в `ComClass1`.  Они будут хранить константы идентификаторов GUID, которые требуются для COM объектов.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  В меню **Сервис** выберите команду **Создать Guid**.  В диалоговом окне **Создать GUID** выберите пункт **Формат реестра** и щелкните **Копировать**.  Нажмите кнопку **Выход**.  
  
5.  Замените пустую строку для `ClassId` на GUID, удалите начальные и конечные фигурные скобки.  Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"`, то код должен выглядеть следующим образом.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Повторите предыдущие шаги для констант `InterfaceId` и `EventsId`, как в следующем примере.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Убедитесь, что GUID являются новыми и уникальными; в противном случае компонент COM может конфликтовать с другими компонентами COM.  
  
7.  Добавьте атрибут `ComClass` к `ComClass1`, задав GUID для Class ID, Interface ID и Events ID, как показано в следующем примере:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Классы COM должны иметь конструктор без параметров `Public Sub New()`, иначе класс не будет регистрироваться правильно.  Добавьте в класс конструктор без параметров:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Добавьте в класс свойства, методы и события и поместите в конце оператор `End Class`.  В меню **Построение** выберите  **Построить решение**.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполнит построение сборки и зарегистрирует объект COM в операционной системе.  
  
    > [!NOTE]
    >  Объекты COM, созданные с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] нельзя использовать с другими приложениями [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], так как они не являются настоящими COM\-объектами.  Попытка добавить ссылку на такие объекты COM вызовет ошибку.  Дополнительные сведения см. в разделе [COM\-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Пошаговое руководство. Реализация наследования с использованием COM\-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md)   
 [COM\-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
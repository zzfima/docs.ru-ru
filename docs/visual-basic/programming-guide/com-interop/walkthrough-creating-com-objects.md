---
title: "Пошаговое руководство: Создание объектов COM с помощью Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cce28e2be5914880107334bf2c4dc4dc645b4793
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Пошаговое руководство. Создание объектов COM с помощью Visual Basic
При создании новых приложений или компонентов, лучше всего создать сборок платформы .NET Framework. Однако [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] также позволяет предоставить доступ к компоненту .NET Framework для COM. Это позволяет создавать новые компоненты для более ранних наборы приложений, требующих COM-компонентов. В этом пошаговом руководстве демонстрируется использование [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для предоставления [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] объектов в виде COM-объектов, как с и без шаблона COM-класса.  
  
 Самый простой способ предоставлять COM-объекты — с помощью шаблона COM-класса. Шаблон COM-класса создает новый класс и затем настраивает проект для создания класса и уровня управляемого взаимодействия как COM-объект и зарегистрировать его с операционной системой.  
  
> [!NOTE]
>  Несмотря на то, что пользователь может предоставить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] как объект COM для использования в неуправляемом коде, не является объектом COM и не может использоваться с [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Чтобы создать объект COM при помощи шаблона класса COM  
  
1.  Откройте новый проект приложения Windows из **файл** меню **новый проект**.  
  
2.  В **новый проект** диалогового окна **типы проектов** поля, проверьте, что выбран Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  Выберите **Добавление нового элемента** из **проекта** меню. **Add New Item** диалоговое окно.  
  
4.  Выберите **COM-класса** из **шаблоны** , а затем нажмите **добавить**. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Добавляет новый класс и настроит новый проект для COM-взаимодействия.  
  
5.  Добавьте код, такие как свойства, методы и события в COM-класс.  
  
6.  Выберите **построить ClassLibrary1** из **построения** меню. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Строит сборку и зарегистрирует объект COM в операционной системе.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Создание объектов COM без шаблона COM-класса  
 Можно также создать класс COM вручную, не используя шаблон COM-класса. Данная процедура будет полезна при работе в командной строке или если требуется больший контроль над определяются как COM-объектов.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Чтобы настроить проект для создания объекта COM  
  
1.  Откройте новый проект приложения Windows из **файл** меню **NewProject**.  
  
2.  В **новый проект** диалогового окна **типы проектов** поля, проверьте, что выбран Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  В **обозревателе решений**щелкните правой кнопкой мыши проект затем **свойства**. **Конструктора проектов** отображается.  
  
4.  Откройте вкладку **Компиляция**.  
  
5.  Выберите **Register for COM Interop** флажок.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Настройка кода в классе для создания объекта COM  
  
1.  В **обозревателе решений**, дважды щелкните **Class1.vb** для просмотра его кода.  
  
2.  Переименуйте класс на `ComClass1`.  
  
3.  Добавьте следующие константы в `ComClass1`. Они будут хранить константы глобальный уникальный идентификатор (GUID), COM-объекты должны иметь.  
  
     [!code-vb[VbVbalrInterop&#2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  На **средства** меню, щелкните **создать Guid**. В **создать GUID** диалоговом нажмите кнопку **формат реестра** и нажмите кнопку **копирования**. Нажмите кнопку **Выход**.  
  
5.  Замените пустую строку для `ClassId` на GUID, удалите начальные и конечные фигурные скобки. Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , а затем код должен выглядеть следующим образом.  
  
     [!code-vb[VbVbalrInterop&#3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Повторите предыдущие шаги для `InterfaceId` и `EventsId` константы, как показано в следующем примере.  
  
     [!code-vb[VbVbalrInterop&#4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Убедитесь, что GUID являются новыми и уникальными; в противном случае — COM-компонент может конфликтовать с другими COM-компонентов.  
  
7.  Добавить `ComClass` атрибут `ComClass1`, указание идентификаторы GUID для идентификатора класса, идентификатор интерфейса и идентификатор события, как в следующем примере:  
  
     [!code-vb[VbVbalrInterop&#5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Классы COM должны иметь конструктор без параметров `Public Sub New()` конструктору, или класс не будет регистрироваться правильно. Добавьте конструктор для класса:  
  
     [!code-vb[VbVbalrInterop №&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Добавьте в класс, в конце свойства, методы и события `End Class` инструкции. Выберите **построить решение** из **построения** меню. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Строит сборку и зарегистрирует объект COM в операционной системе.  
  
    > [!NOTE]
    >  COM-объекты, которые создают с [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не может использоваться другими [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приложений, так как они не являются настоящими COM-объектами. Попытка добавить ссылку на такие объекты COM вызовет ошибку. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>   
 [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)   
 [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)

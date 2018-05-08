---
title: Пошаговое руководство. Создание объектов COM с помощью Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: caf0a071d65746f1027052e648ade538d62dc4bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Пошаговое руководство. Создание объектов COM с помощью Visual Basic
При создании новых приложений или компонентов, лучше создать сборок платформы .NET Framework. Однако Visual Basic также позволяет легко предоставлять компонент .NET Framework для COM. Это позволяет создавать новые компоненты для более ранних наборы приложений, требующих COM-компонентов. В этом пошаговом руководстве демонстрируется использование Visual Basic для предоставления [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] объекты в виде COM-объекты, как с и без шаблона COM-класса.  
  
 С помощью шаблона класса COM — самый простой способ предоставления COM-объектов. Шаблон класса COM создает новый класс и затем настраивает проект для создания класса и взаимодействие слоя как COM-объекта и зарегистрируйте его в операционной системе.  
  
> [!NOTE]
>  Несмотря на то, что также можно представить класс, созданный в Visual Basic как COM-объект для использования в неуправляемом коде, он не является объектом COM и не может использоваться в Visual Basic. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Создание COM-объекта с помощью шаблона класса COM  
  
1.  Откройте новый проект приложения Windows с **файл** меню, щелкнув **новый проект**.  
  
2.  В **новый проект** диалогового окна **типы проектов** поле, убедитесь, что установлен Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  Выберите **Добавление нового элемента** из **проекта** меню. Откроется диалоговое окно **Добавление нового элемента**.  
  
4.  Выберите **COM-класса** из **шаблоны** , а затем нажмите **добавить**. Visual Basic добавит новый класс и настроит новый проект для COM-взаимодействия.  
  
5.  Добавьте код, таких как свойства, методы и события в COM-класс.  
  
6.  Выберите **построить ClassLibrary1** из **построения** меню. Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Создание объектов COM без шаблона класса COM  
 Можно также создать COM-класс вручную, не используя шаблон COM-класса. Данная процедура будет полезна при работе в командной строке или если требуется больший контроль над определение COM-объекты.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Чтобы настроить проект для создания COM-объекта  
  
1.  Откройте новый проект приложения Windows с **файл** меню, щелкнув **NewProject**.  
  
2.  В **новый проект** диалогового окна **типы проектов** поле, убедитесь, что установлен Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  В **обозревателе решений**, щелкните правой кнопкой мыши проект и выберите команду **свойства**. **Конструктора проектов** отображается.  
  
4.  Откройте вкладку **Компиляция**.  
  
5.  Выберите **регистрация для COM-взаимодействия** флажок.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Чтобы настроить код в классе для создания COM-объекта  
  
1.  В **обозревателе решений**, дважды щелкните **Class1.vb** для отображения его код.  
  
2.  Переименуйте класс на `ComClass1`.  
  
3.  Добавьте следующие константы в `ComClass1`. Они будут хранить константы глобальный уникальный идентификатор (GUID), которые должны иметь COM-объекты.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  В меню **Сервис** выберите пункт **Создать GUID**. В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**. Нажмите кнопку **Выход**.  
  
5.  Замените пустую строку для `ClassId` на GUID, удалите начальные и конечные фигурные скобки. Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , а затем код должен выглядеть следующим образом.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Повторите предыдущие шаги для `InterfaceId` и `EventsId` константы, как показано в следующем примере.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Убедитесь, что GUID являются новыми и уникальными; в противном случае компонент COM, могут конфликтовать с другими COM-компонентами.  
  
7.  Добавить `ComClass` атрибут `ComClass1`, указание идентификаторы GUID для ИД класса, интерфейса идентификатор и идентификатор события, как в следующем примере:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Классы COM должны иметь конструктор без параметров `Public Sub New()` конструктору, или класс не будет регистрироваться правильно. Добавьте конструктор для класса:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Добавьте в класс, в конце свойства, методы и события `End Class` инструкции. Выберите **построить решение** из **построения** меню. Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.  
  
    > [!NOTE]
    >  COM-объекты, созданные с помощью Visual Basic не может использоваться другими приложениями Visual Basic, поскольку они не являются настоящими COM-объектами. Попытка добавить ссылку на такие объекты COM, возникнет ошибка. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Пошаговое руководство. Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)  
 [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)

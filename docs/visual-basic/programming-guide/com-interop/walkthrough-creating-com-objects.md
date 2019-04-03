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
ms.openlocfilehash: 5fc0105cffb5606f9382aca7b55d6544d04f9fe7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838161"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Пошаговое руководство. Создание объектов COM с помощью Visual Basic
При создании новых приложений или компонентов, лучше всего создать сборок платформы .NET Framework. Тем не менее Visual Basic также позволяет легко предоставить доступ к компоненту .NET Framework для модели COM. Это позволяет создавать новые компоненты для более ранних пакетов приложений, требующих COM-компонентов. В этом пошаговом руководстве демонстрируется использование Visual Basic для предоставления [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] объектов в виде COM-объектов, как с и без шаблона COM-класса.  
  
 Самый простой способ предоставлять COM-объекты — с помощью шаблона COM-класса. Шаблон класса COM создает новый класс и затем настраивает проект для создания на уровне класса и взаимодействие как объект COM и зарегистрируйте его с операционной системой.  
  
> [!NOTE]
>  Несмотря на то, что можно также предоставлять класс, созданный в Visual Basic как объект COM для неуправляемого кода для использования, он не является истинным COM-объектом и не может использоваться с Visual Basic. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Чтобы создать объект COM с помощью шаблона класса COM  
  
1.  Откройте новый проект приложения Windows из **файл** меню, щелкнув **новый проект**.  
  
2.  В **новый проект** диалогового окна **типы проектов** , убедитесь, что выбран Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  Выберите **Добавление нового элемента** из **проекта** меню. Откроется диалоговое окно **Добавление нового элемента**.  
  
4.  Выберите **COM-класса** из **шаблоны** , а затем нажмите **добавить**. Добавляет новый класс Visual Basic и настраивает новый проект для COM-взаимодействия.  
  
5.  Добавьте код, такие как свойства, методы и события в COM-класс.  
  
6.  Выберите **построения ClassLibrary1** из **построения** меню. Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Создание объектов COM без шаблона COM-класса  
 Также можно создать класс COM вручную, вместо использования шаблона COM-класса. Данная процедура будет полезна при работе из командной строки, или если требуется больший контроль над определение COM-объектов.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Чтобы настроить проект для создания COM-объекта  
  
1.  Откройте новый проект приложения Windows из **файл** меню, щелкнув **NewProject**.  
  
2.  В **новый проект** диалогового окна **типы проектов** , убедитесь, что выбран Windows. Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**. Откроется новый проект.  
  
3.  В **обозревателе решений** щелкните правой кнопкой мыши на проект и выберите пункт **Свойства**. **Конструктор проектов** отображается.  
  
4.  Откройте вкладку **Компиляция**.  
  
5.  Выберите **регистрация для COM-взаимодействия** "флажок".  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Чтобы настроить код в классе для создания COM-объекта  
  
1.  В **обозревателе решений**, дважды щелкните **Class1.vb** для отображения ее кода.  
  
2.  Переименуйте класс на `ComClass1`.  
  
3.  Добавьте следующие константы для `ComClass1`. Они будут храниться константы глобальный уникальный идентификатор (GUID), которые должны иметь COM-объекты.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4.  В меню **Сервис** выберите пункт **Создать GUID**. В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**. Нажмите кнопку **Выход**.  
  
5.  Замените пустую строку для `ClassId` с идентификатором GUID, удалите начальные и конечные фигурные скобки. Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` то ваш код должен выглядеть следующим образом.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6.  Повторите предыдущие шаги для `InterfaceId` и `EventsId` константы, как показано в следующем примере.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  Убедитесь, что значения GUID имеют новыми и уникальными; в противном случае компонент COM могут конфликтовать с другими компонентами COM.  
  
7.  Добавить `ComClass` атрибут `ComClass1`, указав идентификаторы GUID для идентификатора класса, идентификатор интерфейса и идентификатор события, как в следующем примере:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8.  Классы COM должны иметь конструктор без параметров `Public Sub New()` конструктор или класс не будет зарегистрирован правильно. Добавьте конструктор в класс:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Добавьте свойства, методы и события к классу, в конце `End Class` инструкции. Выберите **построить решение** из **построения** меню. Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.  
  
    > [!NOTE]
    >  COM-объекты, созданные с помощью Visual Basic не может использоваться другими приложениями Visual Basic, поскольку они не являются настоящими COM-объектами. Попытка добавить ссылку на такие объекты COM, возникнет ошибка. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)

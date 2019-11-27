---
title: Пошаговое руководство. Создание COM-объектов
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 5d00aff07358a0c40159fde9c12c70e0842d848b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338622"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Пошаговое руководство. Создание объектов COM с помощью Visual Basic
При создании новых приложений или компонентов лучше создавать сборки .NET Framework. Однако Visual Basic также упрощает предоставление .NET Framework компонента COM. Это позволяет предоставлять новые компоненты для более ранних версий приложений, требующих COM-компонентов. В этом пошаговом руководстве показано, как использовать Visual Basic для предоставления объектов .NET Framework в виде COM-объектов как с шаблоном COM-класса, так и без него.  
  
 Самый простой способ предоставить COM-объекты — использовать шаблон COM-класса. Шаблон COM-класса создает новый класс, а затем настраивает проект для создания класса и уровня взаимодействия в виде COM-объекта и его регистрации в операционной системе.  
  
> [!NOTE]
> Хотя можно также предоставить класс, созданный в Visual Basic, как COM-объект для использования неуправляемым кодом, он не является настоящим COM-объектом и не может использоваться Visual Basic. Дополнительные сведения см. [в разделе COM-взаимодействие в .NET Framework приложениях](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Создание COM-объекта с помощью шаблона класса COM  
  
1. Откройте новый проект приложения Windows из меню **файл** , щелкнув **создать проект**.  
  
2. Убедитесь, что в диалоговом окне **Новый проект** в поле **типы проектов** выбрано значение Windows. В списке **шаблоны** выберите пункт **Библиотека классов** , а затем нажмите кнопку **ОК**. Отобразится новый проект.  
  
3. В меню **проект** выберите команду **Добавить новый элемент** . Откроется диалоговое окно **Добавление нового элемента**.  
  
4. Выберите **класс COM** в списке **шаблоны** и нажмите кнопку **добавить**. Visual Basic добавляет новый класс и настраивает новый проект для COM-взаимодействия.  
  
5. Добавьте в класс COM код, например свойства, методы и события.  
  
6. Выберите **Сборка ClassLibrary1** в меню **Сборка** . Visual Basic создает сборку и регистрирует COM-объект в операционной системе.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Создание COM-объектов без шаблона класса COM  
 Можно также создать COM-класс вручную вместо использования шаблона COM-класса. Эта процедура полезна при работе из командной строки или в том случае, если требуется больший контроль над определением объектов COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Настройка проекта для создания COM-объекта  
  
1. Откройте новый проект приложения Windows из меню **файл** , щелкнув **NewProject**.  
  
2. Убедитесь, что в диалоговом окне **Новый проект** в поле **типы проектов** выбрано значение Windows. В списке **шаблоны** выберите пункт **Библиотека классов** , а затем нажмите кнопку **ОК**. Отобразится новый проект.  
  
3. В **обозревателе решений** щелкните правой кнопкой мыши на проект и выберите пункт **Свойства**. Откроется **Конструктор проектов** .  
  
4. Откройте вкладку **Компиляция**.  
  
5. Установите флажок **Регистрация для COM-взаимодействия** .  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Настройка кода в классе для создания COM-объекта  
  
1. В **Обозреватель решений**дважды щелкните **Class1. vb** , чтобы отобразить его код.  
  
2. Переименуйте класс на `ComClass1`.  
  
3. Добавьте следующие константы в `ComClass1`. Они будут хранить константы глобального уникального идентификатора (GUID), которые должны иметь объекты COM.  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. В меню **Сервис** выберите пункт **Создать GUID**. В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**. Нажмите кнопку **Выход**.  
  
5. Замените пустую строку `ClassId` идентификатором GUID, удаляя начальные и конечные фигурные скобки. Например, если идентификатор GUID, предоставленный Guidgen, — `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` то код должен выглядеть следующим образом.  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. Повторите предыдущие шаги для констант `InterfaceId` и `EventsId`, как показано в следующем примере.  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > Убедитесь, что идентификаторы GUID являются новыми и уникальными. в противном случае COM-компонент может конфликтовать с другими COM-компонентами.  
  
7. Добавьте атрибут `ComClass` в `ComClass1`, указав идентификаторы GUID для идентификатора класса, идентификатора интерфейса и идентификатора события, как показано в следующем примере:  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. Классы COM должны иметь `Public Sub New()` конструктор без параметров, иначе класс не будет зарегистрирован правильно. Добавьте в класс конструктор без параметров:  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. Добавьте свойства, методы и события в класс, завершая его оператором `End Class`. В меню **Сборка** выберите пункт **построить решение** . Visual Basic создает сборку и регистрирует COM-объект в операционной системе.  
  
    > [!NOTE]
    > Объекты COM, созданные с помощью Visual Basic, не могут использоваться другими приложениями Visual Basic, поскольку они не являются настоящими COM-объектами. Попытка добавить ссылки на такие COM-объекты вызовет ошибку. Дополнительные сведения см. [в разделе COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Пошаговое руководство. Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)

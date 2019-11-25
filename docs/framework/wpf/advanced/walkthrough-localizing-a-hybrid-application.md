---
title: Пример локализации гибридного приложения
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 281afad0c0de856ca67abc74c65aff0e7afc3e01
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976501"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Пример локализации гибридного приложения

В этом пошаговом руководстве показано, как локализовать элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в гибридном приложении на основе [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] узла.

- Добавление локализуемого содержимого.

- Включение локализации.

- Назначение идентификаторов ресурсов.

- Использование средства LocBaml для создания вспомогательной сборки.

Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Локализация примера гибридного приложения](https://go.microsoft.com/fwlink/?LinkID=160015).

Закончив, вы получите локализованное гибридное приложение.

## <a name="prerequisites"></a>Необходимые компоненты

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Создание ведущего проекта Windows Forms

Первым шагом является создание проекта приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и Добавление элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с содержимым, которое будет локализовано.

### <a name="to-create-the-host-project"></a>Создание ведущего проекта

1. Создайте проект **приложения WPF** с именем `LocalizingWpfInWf`.  (**Файл** > **Новый** > **проект** > **Visual C#**  или **Visual Basic** > **классическое** **приложение WPF**).

2. Добавьте в проект элемент <xref:System.Windows.Controls.UserControl> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]с именем `SimpleControl`.

3. Используйте элемент управления <xref:System.Windows.Forms.Integration.ElementHost>, чтобы поместить элемент `SimpleControl` в форму. Дополнительные сведения см. [в разделе Пошаговое руководство. Размещение трехмерного составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Добавление локализуемого содержимого

Далее предстоит добавить элемент управления Label [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и задать содержимое элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для локализуемой строки.

### <a name="to-add-localizable-content"></a>Добавление локализуемого содержимого

1. В **Обозреватель решений**дважды щелкните **SimpleControl. XAML** , чтобы открыть его в конструкторе WPF.

2. Задайте содержимое элемента управления <xref:System.Windows.Controls.Button> с помощью следующего кода.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. В **Обозреватель решений**дважды щелкните **Form1** , чтобы открыть его в конструктор Windows Forms.

4. Откройте **панель элементов** и дважды щелкните **подпись** , чтобы добавить в форму элемент управления "надпись". Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.

5. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

     Элемент `SimpleControl` и элемент управления Label отображают текст **"Hello"** .

## <a name="enabling-localization"></a>Включение локализации

Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.

### <a name="to-enable-localization"></a>Включение локализации

1. В **Обозреватель решений**дважды щелкните **Form1.CS** , чтобы открыть его в конструктор Windows Forms.

2. В окне **Свойства** задайте для свойства **localizable** формы значение `true`.

3. В окне **Свойства** задайте для свойства **язык** значение **Испанский (Испания)** .

4. В конструкторе Windows Forms выберите элемент управления label.

5. В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> значение `"Hola"`.

     Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.

6. В **Обозреватель решений**щелкните правой кнопкой мыши **Form1.CS** и выберите пункт **Просмотреть код** , чтобы открыть его в редакторе кода.

7. Скопируйте следующий код в конструктор `Form1`, предшествующий вызову `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. В **Обозреватель решений**щелкните правой кнопкой мыши **LocalizingWpfInWf** и выберите команду **Выгрузить проект**.

     Имя проекта помечено как **(недоступно)** .

9. Щелкните правой кнопкой мыши **LocalizingWpfInWf**и выберите **изменить LocalizingWpfInWf. csproj**.

     Файл проекта откроется в редакторе кода.

10. Скопируйте следующую строку в первую `PropertyGroup` в файле проекта.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Сохраните файл проекта и закройте его.

12. В **Обозреватель решений**щелкните правой кнопкой мыши **LocalizingWpfInWf** и выберите **Перезагрузить проект**.

## <a name="assigning-resource-identifiers"></a>Назначение идентификаторов ресурсов

Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов. Приложение MsBuild. exe автоматически назначает идентификаторы ресурсов при указании параметра `updateuid`.

### <a name="to-assign-resource-identifiers"></a>Назначение идентификаторов ресурсов

1. В меню Пуск откройте Командная строка разработчика для Visual Studio.

2. Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. В **Обозреватель решений**дважды щелкните **SimpleControl. XAML** , чтобы открыть его в редакторе кода. Вы увидите, что команда `msbuild` добавила атрибут `Uid` ко всем элементам. Это облегчает локализацию через назначение идентификаторов ресурсов.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Нажмите клавишу **F6** , чтобы создать решение.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Использование LocBaml для создания вспомогательной сборки

Локализованное содержимое хранится в *вспомогательной сборке*с ресурсами только для ресурсов. Используйте программу командной строки LocBaml. exe для создания локализованной сборки для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="to-produce-a-satellite-assembly"></a>Создание вспомогательной сборки

1. Скопируйте файл LocBaml.exe в папку проекта obj\Debug. Дополнительные сведения см. в разделе [Локализация приложения](how-to-localize-an-application.md).

2. В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Откройте файл TEMP. csv в Visual Studio или другом текстовом редакторе. Замените строку `"Hello"` на ее Испанский перевод, `"Hola"`.

4. Сохраните файл temp.csv.

5. Используйте приведенную ниже команду для создания локализованного файла ресурса.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.

6. Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.

7. Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES. Замените существующий файл.

8. Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug. Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.

     В приложении выводятся локализованные строки вместо английских строк.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Локализация приложения](how-to-localize-an-application.md)
- [Пошаговое руководство. Локализация Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)

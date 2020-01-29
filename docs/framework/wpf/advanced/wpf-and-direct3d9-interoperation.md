---
title: Взаимодействие WPF и Direct3D9
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 9ec83c48052e1ef29bb91a6b40b7c76f671bb99f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735183"
---
# <a name="wpf-and-direct3d9-interoperation"></a>Взаимодействие WPF и Direct3D9
Содержимое Direct3D9 можно включить в приложение Windows Presentation Foundation (WPF). В этом разделе описывается создание содержимого Direct3D9 для эффективного взаимодействия с WPF.  
  
> [!NOTE]
> При использовании содержимого Direct3D9 в WPF также необходимо подумать о производительности. Дополнительные сведения о том, как оптимизировать производительность, см. в статье вопросы производительности, связанные с [взаимодействием Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Отобразить буферы  
 Класс <xref:System.Windows.Interop.D3DImage> управляет двумя буферами вывода, которые называются *задним* и *передним*буфером. Задний буфер — это поверхность Direct3D9. Изменения заднего буфера копируются прямо в передний буфер при вызове метода <xref:System.Windows.Interop.D3DImage.Unlock%2A>.  
  
 На следующем рисунке показана связь между задним буфером и передним буфером.  
  
 ![D3DImage буферы экрана](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Создание устройства Direct3D9  
 Для отображения содержимого Direct3D9 необходимо создать устройство Direct3D9. Существует два объекта Direct3D9, которые можно использовать для создания устройства, `IDirect3D9` и `IDirect3D9Ex`. Используйте эти объекты для создания `IDirect3DDevice9` и `IDirect3DDevice9Ex` устройств соответственно.  
  
 Создайте устройство, вызвав один из следующих методов.  
  
- `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
- `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 В операционной системе Windows Vista или более поздней версии используйте метод `Direct3DCreate9Ex` с отображением, настроенным для использования модели Windows дисплея (WDDM). Используйте метод `Direct3DCreate9` на любой другой платформе.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Доступность метода Direct3DCreate9Ex  
 D3d9. dll содержит метод `Direct3DCreate9Ex` только в Windows Vista или более поздней версии операционной системы. Если вы напрямую свяжете функцию в Windows XP, приложение не сможет загрузиться. Чтобы определить, поддерживается ли метод `Direct3DCreate9Ex`, загрузите библиотеку DLL и найдите адрес процедуры. В следующем коде показано, как проверить метод `Direct3DCreate9Ex`. Полный пример кода см. в разделе [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Создание HWND  
 Для создания устройства требуется HWND. Как правило, для использования Direct3D9 создается фиктивный HWND. В следующем примере кода показано, как создать фиктивный HWND.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Существующие параметры  
 Для создания устройства также требуется структура `D3DPRESENT_PARAMETERS`, но важны только несколько параметров. Эти параметры выбраны для минимального объема памяти.  
  
 Задайте для полей `BackBufferHeight` и `BackBufferWidth` значение 1. Если задать для них значение 0, то для них будут заданы размеры HWND.  
  
 Всегда устанавливайте флаги `D3DCREATE_MULTITHREADED` и `D3DCREATE_FPU_PRESERVE`, чтобы избежать повреждения памяти, используемой Direct3D9, и предотвращения изменения параметров FPU в Direct3D9.  
  
 В следующем коде показано, как инициализировать структуру `D3DPRESENT_PARAMETERS`.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Создание целевого объекта рендеринга заднего буфера  
 Чтобы отобразить содержимое Direct3D9 в <xref:System.Windows.Interop.D3DImage>, создайте поверхность Direct3D9 и назначьте ее, вызвав метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
### <a name="verifying-adapter-support"></a>Проверка поддержки адаптера  
 Перед созданием поверхности убедитесь, что все адаптеры поддерживают требуемые свойства поверхности. Даже если вы отрисовываете только один адаптер, окно WPF может отображаться на любом адаптере в системе. Всегда следует писать код Direct3D9, который обрабатывает конфигурации с несколькими адаптерами, и следует проверять поддержку всех адаптеров, так как WPF может перемещать поверхность между доступными адаптерами.  
  
 В следующем примере кода показано, как проверить все адаптеры в системе для поддержки Direct3D9.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Создание поверхности  
 Перед созданием поверхности убедитесь, что возможности устройства поддерживают хорошую производительность в целевой операционной системе. Дополнительные сведения см. в разделе [вопросы производительности для совместимости с Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 После проверки возможностей устройства можно создать поверхность. В следующем примере кода показано, как создать целевой объект отрисовки.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>ДРАЙВЕР  
 В Windows Vista и более поздних операционных системах, настроенных для использования WDDM, можно создать текстуру целевого объекта рендеринга и передать поверхность уровня 0 в метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>. Этот подход не рекомендуется в Windows XP, так как нельзя создать блокируемую текстуру целевого объекта рендеринга, и производительность будет снижена.  
  
## <a name="handling-device-state"></a>Обработка состояния устройства  
 Класс <xref:System.Windows.Interop.D3DImage> управляет двумя буферами вывода, которые называются *задним* и *передним*буфером. Задний буфер — это поверхность Direct3D.  Изменения заднего буфера копируются прямо в передний буфер при вызове метода <xref:System.Windows.Interop.D3DImage.Unlock%2A>, где он отображается на оборудовании. Иногда передний буфер становится недоступным. Отсутствие доступности может быть вызвано блокировкой экрана, полноэкранным эксклюзивным приложением Direct3D, переключением пользователей или другими системными действиями. В этом случае приложение WPF будет уведомлено, обрабатывая событие <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>.  То, как приложение реагирует на передний план, становится недоступным, зависит от того, включена ли платформа WPF для возврата к отрисовке программного обеспечения. Метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> имеет перегрузку, которая принимает параметр, указывающий, возвращается ли WPF к отрисовке программного обеспечения.  
  
 При вызове перегрузки <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> или вызове перегрузки <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> с параметром `enableSoftwareFallback`, для которого задано значение `false`, система отрисовки освобождает ссылку на задний буфер, когда передний буфер становится недоступным и ничего не отображается. Когда передний буфер снова становится доступным, система визуализации создает событие <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> для уведомления приложения WPF.  Для события <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> можно создать обработчик событий, чтобы снова перезапустить визуализацию с допустимой поверхностью Direct3D. Чтобы перезапустить подготовку к просмотру, необходимо вызвать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 При вызове перегрузки <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> с параметром `enableSoftwareFallback`, для которого задано значение `true`, система визуализации оставляет ссылку на задний буфер, когда передний буфер становится недоступным, поэтому нет необходимости вызывать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> при повторном доступе переднего буфера.  
  
 При включенной отрисовке программного обеспечения могут возникнуть ситуации, когда устройство пользователя становится недоступным, но система визуализации оставляет ссылку на поверхность Direct3D. Чтобы проверить, недоступно ли устройство Direct3D9, вызовите метод `TestCooperativeLevel`. Чтобы проверить устройства Direct3D9Ex, вызовите метод `CheckDeviceState`, так как метод `TestCooperativeLevel` является устаревшим и всегда возвращает значение Success. Если пользовательское устройство становится недоступным, вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>, чтобы освободить ссылку WPF на задний буфер.  Если необходимо сбросить устройство, вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> с параметром `backBuffer`, для которого задано значение `null`, а затем снова вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>, указав для `backBuffer` значение допустимой поверхности Direct3D.  
  
 Вызовите метод `Reset` для восстановления из недопустимого устройства только в том случае, если вы реализуете поддержку нескольких адаптеров. В противном случае освободите все интерфейсы Direct3D9 и создайте их заново. Если макет адаптера изменился, объекты Direct3D9, созданные до изменения, не будут обновлены.  
  
## <a name="handling-resizing"></a>Обработка изменения размера  
 Если <xref:System.Windows.Interop.D3DImage> отображается с разрешением, отличным от его собственного размера, оно масштабируется в соответствии с текущей <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, за исключением того, что <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> подставляется для <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Если требуется более высокая точность, необходимо создать новую поверхность, когда контейнер <xref:System.Windows.Interop.D3DImage> изменит размер.  
  
 Существует три возможных подхода к изменению размера.  
  
- Примите участие в системе макета и создайте новую поверхность при изменении размера. Не создавайте слишком много поверхностей, так как вы можете израсходованиь или фрагментировать видеопамять.  
  
- Дождитесь возникновения события изменения размера в течение фиксированного периода времени, чтобы создать новую поверхность.  
  
- Создайте <xref:System.Windows.Threading.DispatcherTimer>, который будет проверять размеры контейнера несколько раз в секунду.  
  
## <a name="multi-monitor-optimization"></a>Оптимизация нескольких мониторов  
 Если система отрисовки перемещает <xref:System.Windows.Interop.D3DImage> на другой монитор, может возникнуть существенно сниженная производительность.  
  
 В WDDM при условии, что мониторы находятся на одном видеоадаптере и вы используете `Direct3DCreate9Ex`, снижение производительности не уменьшается. Если мониторы находятся на разных видеоадаптерах, производительность снижается. В Windows XP производительность всегда снижается.  
  
 Когда <xref:System.Windows.Interop.D3DImage> перемещается на другой монитор, можно создать новую поверхность на соответствующем адаптере, чтобы восстановить хорошую производительность.  
  
 Чтобы избежать снижения производительности, напишите код специально для случая с несколькими мониторами. В следующем списке показан один из способов написания кода для нескольких мониторов.  
  
1. Найдите точку <xref:System.Windows.Interop.D3DImage> в пространстве экрана с помощью метода `Visual.ProjectToScreen`.  
  
2. Используйте `MonitorFromPoint`ный метод GDI для поиска монитора, который отображает точку.  
  
3. Используйте метод `IDirect3D9::GetAdapterMonitor`, чтобы найти адаптер Direct3D9, на котором находится монитор.  
  
4. Если адаптер не совпадает с адаптером с задним буфером, создайте новый задний буфер на новом мониторе и назначьте его буферу <xref:System.Windows.Interop.D3DImage>.  
  
> [!NOTE]
> Если <xref:System.Windows.Interop.D3DImage> повлечет за собой мониторы, производительность будет снижена, за исключением случаев WDDM и `IDirect3D9Ex` на одном адаптере. В этой ситуации невозможно повысить производительность.  
  
 В следующем примере кода показано, как найти текущий монитор.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Обновляйте монитор при изменении размера или расположения контейнера <xref:System.Windows.Interop.D3DImage> или при обновлении монитора с помощью `DispatcherTimer`, который обновляется несколько раз в секунду.  
  
## <a name="wpf-software-rendering"></a>Программная отрисовка WPF  
 WPF выполняет визуализацию синхронно в потоке пользовательского интерфейса в программном обеспечении в следующих ситуациях.  
  
- Печать  
  
- <xref:System.Windows.Media.Effects.BitmapEffect>  
  
- <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Когда происходит одна из этих ситуаций, система визуализации вызывает метод <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> для копирования аппаратного буфера в программное обеспечение. Реализация по умолчанию вызывает метод `GetRenderTargetData` с вашей поверхностью. Так как этот вызов происходит вне шаблона блокировки или блокирования, он может завершиться ошибкой. В этом случае метод `CopyBackBuffer` возвращает `null` и изображение не отображается.  
  
 Можно переопределить метод <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>, вызвать базовую реализацию и, если она возвращает `null`, можно вернуть заполнитель <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 Можно также реализовать собственную отрисовку программного обеспечения вместо вызова базовой реализации.  
  
> [!NOTE]
> Если WPF полностью готовится к просмотру в программном обеспечении, <xref:System.Windows.Interop.D3DImage> не отображается, поскольку в WPF отсутствует интерфейсный буфер.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Interop.D3DImage>
- [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)

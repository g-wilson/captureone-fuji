# captureone-fuji
Capture One presets for Fuji X-Trans cameras

## Presets

### Curves

#### Dynamic Range Priority: Weak (X-Trans 4)

This curve emulates the luminance adjustment made by my X-T30ii when exporting JPEGs with Dynamic Range Priority set to `Weak`. Shadows are boosted nicely but overall contrast still remains.

#### Dynamic Range Priority: Strong (X-Trans 4)

This curve emulates the luminance adjustment made by my X-T30ii when exporting JPEGs with Dynamic Range Priority set to `Strong`. It produces a very flat image with little contrast.

## Notes

### Dynamic Range Priroity

The Dynamic Range Priority in X-Trans cameras works by applying a luminosity curve (gamma adjustment) to tone-map the raw sensor in order to achieve a "flatter" resulting image for JPEG export. Effectively it reduces overall image contrast by brightening shadows and darkening highlights.

When shooting in RAW, the in-camera previews display with this adjustment however it is not reflected in editing applications.

When shooting with Dynamic Range Priority in `Weak` or `Strong`, the Dynamic Range setting is forced to `Auto`.

### Dynamic Range DR200 / DR400 handling in RAW files

The Dynamic Range setting in X-Trans cameras works by shooting in a higher ISO mode than chosen by the user, and then underexposing the image. When exporting as JPEG, or previewing the RAW image in-camera, the processor adjusts the exposure gain of the RAW file by the equivalent number of stops that it underexposed the image at capture time. The result is an image with a perceptually identical exposure on export or preview, but much more image data in areas of the image with higher luminosity (highlights).

- Capture One Pro
  - C1 Pro treats each dynamic range setting as a separate RAW file format. When previewing RAW files with `DR200` or `DR400`, it automatically adjusts the exposure gain (+1 stop for `DR200`, +2 stops for `DR400`) to reflect the preview as seen in-camera.

- Capture One Express
  - C1 Express for Fujifilm only has one RAW file format. As a result, RAW images captured at `DR200` and `DR400` appear _underexposed_. The user is required to adjust the exposure gain within Capture One (+1 for `DR200`, +2 for `DR400`) to approximately achieve the equivalent perceptual exposure as shown in JPEGs, in-camera previews, and Capture One Pro.

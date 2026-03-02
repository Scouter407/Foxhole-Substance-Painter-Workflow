# Foxhole-Substance-Painter-Workflow
Guide for using Substance Painter to texture in Foxhole with resources.

# Overview 
Substance Painter Export Preset is in the releases section, alongside the filter stack you place at the top of your texture layers. This should be a general overview for people who are already a bit familiar with Substance Painter. If you ever want feedback or help with a texture in Substance Painter, my discord is scouter407, I'm avaliable.

## C Map:
Base color, this should have good contrast, Foxhole uses PBR but seems to lack a strong lighting system to allow for everything to be visible, so a lot of contrast variation has to be baked on, which is done with the Filter Stack.

## N Map:
Normal map, DirectX format, stronger normal details seem to play well into the flatter lighting system, most likely due to the lower poly surfaces that need to look detailed in game.

## M Map:
Material map, this is what defines all the PBR values outside of base color and normals:

  - Red channel is Metallic, which is a grayscale map that defines how metal an object is. 0 (Black) is something completely non-metal, like a brick or a piece of wood, and 1 (White) is fully metallic, like a piece of newly machined aluminum.
  
  - Green channel is Roughness, which is a grayscale map that defines how rough or smooth an object is. 0 (Black) is a completely smooth polished object, like a mirror, and 1 (White) is fully rough, like dried out earth, lacking any highlights.
  
  - Blue channel is most of the time Ambient Occlusion, which is a grayscale map that shows what areas on the mesh should be occluded, or naturally darker due to light being blocked by something nearby. This is for shadowing baked onto the texture, and is most of the        time done purely from the Substance Painter by baking the mesh maps.
  - Blue channel is sometimes not Ambient Occlusion, mostly on vehicles, where it is instead a mask texture for the veteran variant of the vehicle. 0 (Black) means the camo isn't in those places, and 1 (White) means the camo is applied to those places.

(Why they remove Ambient Occlusion from vehicles I have no clue, it doesn't really make sense when you could use a separate texture or even a procedural for the veteran camo.)

  - Alpha Channel is Opacity, 0 (Black) means you can see through the object, and 1 (White) means you can't see through it. I'd advise against adding opacity to meshes that previously didn't have it, as most of the time it requires some extra work to look normal.

## Substance Painter Specifics:
I use the Studio Automotive Neutral for my environment texture, as it mimics how Foxhole lacks strong directional lighting and does tend to rely mostly on color within the texture for saturation. Some specifics about the Filter Stack are as follows, I'd suggest playing around with some variables like the opacity of the AO layer, the contrast on the Contrast Luminosity (though it should be at a good value for most textures), but I'd suggest leaving the Baked Lighting Stylized alone as I believe it's worked pretty well so far. The Roughness Tweak levels can also be played with purely based on the style you want. This will not make your texture automatically look amazing, but it does give it a strong help to unify the texture with lighting, as displayed by the images below. If you want to texture a veteran vehicle, I'd suggest exporting as normal and then painting the veteran texture into the base color in a new folder, using only grayscale values, export that separately and copy it into the blue channel of your M texture map.

## Example
Substance Painter with the filter stack:
<img width="2030" height="1089" alt="image" src="https://github.com/user-attachments/assets/ba0ead1e-72fc-4c39-b685-7687fcc9f2e5" />
Substance Painter without the filter stack:
<img width="2037" height="1088" alt="image" src="https://github.com/user-attachments/assets/88e3dcbe-8d0f-4288-9b0f-6bcca185900d" />

## Usage Terms: 
If you use this in a project, all I ask is that you credit this page so others can find it and use it for their projects.

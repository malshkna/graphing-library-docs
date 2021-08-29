---
layout: post
title:  MATLAB waterfall
description: Learn how to make 4 waterfall charts in MATLAB, then publish them to the Web with Plotly.
permalink: /matlab/surface-and-mesh-plots/waterfall/
layout: matlab
function: waterfall
reference: https://mathworks.com/help/matlab/ref/waterfall.html
github: surface-and-mesh-plots/2021-08-29-waterfall.md
---

## Create Waterfall Plot

> Create three matrices of the same size. Then plot them as a waterfall plot. The mesh plot uses `Z` for both height and color.

<pre class="mcode">
  [X,Y] = meshgrid(-3:.125:3);
Z = peaks(X,Y);
waterfall(X,Y,Z)
fig2plotly()
</pre>

{% include posts/ssim_frame.html 
  src="https://chart-studio.plotly.com/~danton267/880.embed" 
  ssim="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_0_0_create_waterfall_plot_montage.png" 
  compare="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_0_0_create_waterfall_plot_ssim_map.png" 
  index=657
%}



<!--------------------- EXAMPLE BREAK ------------------------->

## Specify Colormap Colors

> Specify the colors for a waterfall plot by including a fourth matrix input, `C`. The waterfall plot uses `Z` for height and `C` for color. Add a color bar to the graph to show how the data values in `C` correspond to the colors in the colormap.

<pre class="mcode">
  [X,Y] = meshgrid(-3:.125:3);
Z = peaks(X,Y);
C = gradient(Z);
waterfall(X,Y,Z,C)
colorbar
fig2plotly()
</pre>

{% include posts/ssim_frame.html 
  src="https://chart-studio.plotly.com/~danton267/882.embed" 
  ssim="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_1_0_specify_colormap_colors_montage.png" 
  compare="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_1_0_specify_colormap_colors_ssim_map.png" 
  index=658
%}



<!--------------------- EXAMPLE BREAK ------------------------->

## Modify Plot Appearance

> Create a waterfall plot. To allow further modifications, assign the patch object to the variable `p`.

<pre>
  [X,Y] = meshgrid(-5:.5:5);
Z = Y.*sin(X) - X.*cos(Y);
p = waterfall(X,Y,Z)
</pre>

{% include posts/ssim_frame.html 
  src="https://chart-studio.plotly.com/~danton267/884.embed" 
  ssim="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_2_0_modify_plot_appearance_montage.png" 
  compare="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_2_0_modify_plot_appearance_ssim_map.png" 
  index=659
%}

<pre>
  <div class="codeoutput"><pre>p = 
  Patch with properties:

    FaceColor: [1 1 1]
    FaceAlpha: 1
    EdgeColor: <span style='color:#A020F0'>'flat'</span>
    LineStyle: '-'
        Faces: [21x26 double]
     Vertices: [546x3 double]

  Show all properties

</pre></div>
</pre>

> Use `p` to access and modify properties of the waterfall plot after it is created. For example, change the color of the plot edges by setting the `EdgeColor` property.

<pre class="mcode">
  p.EdgeColor = <span style='color:#A020F0'>'b'</span>;
fig2plotly()
</pre>

{% include posts/ssim_frame.html 
  src="https://chart-studio.plotly.com/~danton267/886.embed" 
  ssim="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_2_1_modify_plot_appearance_montage.png" 
  compare="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_2_1_modify_plot_appearance_ssim_map.png" 
  index=660
%}



<!--------------------- EXAMPLE BREAK ------------------------->

## Change Curtain Location

> Display a partial curtain along the *x*-dimension (instead of the *y*-dimension) by transposing the input arguments.

<pre class="mcode">
  [X,Y] = meshgrid(-3:.125:3);
Z = peaks(X,Y);
waterfall(X',Y',Z')
fig2plotly()
</pre>

{% include posts/ssim_frame.html 
  src="https://chart-studio.plotly.com/~danton267/888.embed" 
  ssim="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_3_0_change_curtain_location_montage.png" 
  compare="https://raw.githubusercontent.com/plotly/ssim_baselines/main/out_matlab/matlab/code-examples/surface-and-mesh-plots/waterfall/plot_3_0_change_curtain_location_ssim_map.png" 
  index=661
%}



<!--------------------- EXAMPLE BREAK ------------------------->

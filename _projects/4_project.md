---
layout: page
title: cbs-xtrapol
description: <b>2023 | extrapolation of Gaussian/exponential properties | </b> suitable for aVnDZ basis sets (n=2-6); fits/plots CBS data vs experimental values.
img: assets/img/1cat_p6bw.jpg
importance: 3
category: new projects
---
<div style="text-align: justify; font-size: 15px; margin-bottom: 2em;">
Peterson et al.'s seminal study introduced the Complete Basis Set (CBS) extrapolation technique, enabling highly accurate predictions of molecular properties through correlation consistent basis sets such as aug-cc-pV(<i>n</i>)Z. Focusing on the <b>H + H<sub>2</sub> = H<sub>2</sub> + H</b>  exchange reaction, their method yielded a CBS barrier height at 9.6 kcal/mol, a value that compares well with the experimental value of 9.62 kcal/mol [Peterson,<i>J.Chem.Phys.</i> 100, 7410, 1994]. Expanding on this scheme, we applied a similar CBS extrapolation method to the hydrogen sulphide dimerization reaction <b>2H<sub>2</sub>S = (H<sub>2</sub>S)<sub>2</sub></b>. This work culminated in a recent JCP publication, in which we reported the CCSD(T)/CBS level binding energy  D<sub>o</sub>=1.08 kcal/mol, which is only 0.6 kcal/mol smaller than the measured value D<sub>o</sub>=1.7±0.3 kcal/mol, and for the first time, its complete anharmonic vibrational spectra [Lemke, <i>J.Chem.Phys.</i> 145, 234301, 2017].
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
    <b>Fig.1/2</b> The cover image to the left is a sniplet of the JPC paper by Peterson et al. that introduced the CBS extrapolation method to compute molecular properties with correlation consistent basis sets, exemplified in the classical barrier height calculation for <b>H+H<sub>2</sub> = H<sub>2</sub>+H</b>. Extending this, we employed the a similar CBS method to the geochemically important <b>2H<sub>2</sub>S </b>dimer, illustrating the method's broad applicability in calculating  accurate binding energies and spectroscopic properties. The four images below showcase related results for <b>SO<sub>2</sub></b> and the dimer (<b>SO<sub>2</sub>)<sub>2</sub></b> derived from the CBS extrapolations scheme and its implementation in python. The script uses import data from G16 and C4 CCSD(T) equilibrium geometry optimisations and anharmonic vibrational frequency calculations and computes the complete basis limit value of each property independently using an exponential decay function.
</div>

<div class="caption">
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS4.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
    <b>Fig.3/4</b> CCSDT/aV(n+d)Z analysis showcasing the convergence of calculated S-O bond distances (left) and (SO2)2 binding energies (right) towards the CBS limits of 1.4333 Å and -2.78 kcal/mol, respectively, against experimental values of 1.4307 Å and -2.82 kcal/mol, and emphasizing the precision of CBS extrapolation in quantum chemical calculations.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CBS/CBS6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
    <b>Fig.5/6</b> Anharmonic CCSDT/aV(n+d)Z level vibrational frequencies, sym. stretch, for the sulphur dioxide isotopologues, 
    <sup>32</sup>S<sup>16</sup>O<sup>16</sup>O (left) and <sup>33</sup>S<sup>18</sup>O<sup>18</sup>O (right). For the former converging to a CBS limit of 1156.9 cm<sup>-1</sup>, against an experimental value of 1151.7 cm<sup>-1</sup>; as seen for <sup>33</sup>S<sup>18</sup>O<sup>18</sup>O, the sym. stretch approaches a CBS limit value of 1101.0 cm<sup>-1</sup>, slightly exceeding the experimental determination of 1093.5 cm<sup>-1</sup>.
</div>

<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
<b>Synopsis:</b> The script uses the Complete Basis Set (CBS) extrapolation method proposed my Peterson, which relies on a exponential decay function that models the convergence behavior of any given property of interest as the basis set size increases from n=2, 3, 4 up to n=5. The function has the form:

$$
De(n) = De(\infty) + A \cdot e^{-(n - 1)} + B \cdot e^{-(n - 1)^2}
$$

where De(n) represents the property value for a given cardinal number n, De(∞) is the CBS limit (the value as n approaches infinity), and A and B are adjustable parameters. The script employs the SciPy library's curve_fit function to optimize the parameters De(∞), A, and B by minimizing the residuals between the input data and the model function. The image below shows a snipplet of the script running on replit using a collaborative browser-based IDE. The displayed output shows the script's interactive prompt for user input and subsequent computation of the CBS limit, with visual output comparing theoretical estimates to experimental data. 
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/CBS/CBS7.jpg" title="example image" class="img-fluid w-100" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
    <b>Fig.7</b> Sniplet of the python script (right) that calculates the CBS extrapolation to estimate various molecular properties, such as structures, energies, polarisabilities, dipole moments, vibrational frequencies (left), by fitting an exponential decay model to ab intio data, and then contrasts these findings with experimental determinations.
</div>

Using the code is quite simple. Just go to <a href="https://replit.com/@konolemke/CBSExtrapolation">replit.com</a> execute `<main.py>` and open a new `<console>` window so that you can execute the script and visualise your results in the `<output console>`. You are expected to input the `number of points` (basis set range) for the CBS extrapolation, the starting `cardinal number` (basis set) and the `experimental value` against which to evaluate the script's calculations.

To generate images in this script,you will need to enter property and plot title when prompted: `property_name = input("Enter the property you want to calculate"` (e.g. S-O bond distance) and `title_name = input("Enter the title for the plot:"`); these inputs will customize your plot output to reflect specific data and analysis focus.

The complete basis set (CBS) extrapolation calculation is performed within the `cbs_extrapolation` function and the `cbs_extrapolation_function` it calls for the curve fitting process. These are the script section where the CBS fit calculation and takes place:

````markdown
```python
def cbs_extrapolation_function(n, De_inf, A, B):
  return De_inf + A * np.exp(-(n - 1)) + B * np.exp(-(n - 1)**2)

def cbs_extrapolation(n_values, energies):
  initial_guess = [energies[-1], 1, 1]  # Initial guess for De(∞), A, and B

  # Curve fitting to obtain De(∞), A, and B values
  popt, _ = curve_fit(cbs_extrapolation_function,
                      n_values,
                      energies,
                      p0=initial_guess)

  return popt  # Return the optimized parameters
```
````
This script section below, defined by the `plot_data function`, is responsible for visualizing the results of the CBS extrapolation alongside experimental data for comparison.

````markdown
```python
def plot_data(n_values, energies, popt, experimental_value, property_name,
              title_name):
  De_CBS_limit = popt[0]
  basis_sets = ['aVDZ', 'aVTZ', 'aVQZ', 'aV5Z', 'aV6Z']
  fitted_n_values = np.linspace(n_values[0] - 0.5, n_values[-1] + 0.5, 100)
  fitted_energies = cbs_extrapolation_function(fitted_n_values, *popt)

  plt.plot(n_values, energies, 'ro', label=f'{property_name} values')
  plt.plot(fitted_n_values,
           fitted_energies,
           'b-',
           label='Fitted CBS Extrapolation')
  plt.axhline(De_CBS_limit,
              color='g',
              linestyle='--',
              label=f'{property_name} (CBS limit) = {De_CBS_limit:.6f}')
  plt.axhline(experimental_value,
              color='m',
              linestyle=':',
              label=f'Experimental value = {experimental_value:.6f}')
  plt.xticks(n_values, basis_sets[:len(n_values)])
  plt.xlabel('Basis Sets')
  plt.ylabel(property_name)
  plt.title(
      f'{title_name}')  # Use the title_name variable for the figure title
  plt.legend()
  plt.grid()
  plt.show(block=True)
```
````


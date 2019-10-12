# Multilingual Question Answering

This repository contains ressources for question answering in multiple languages. 

## Data

In the data folder, there are 9 monolingual or cross-lingual datasets, based on SQuAD v1.1 dev set (https://rajpurkar.github.io/SQuAD-explorer/explore/1.1/dev/) and its translations on French and Japanese from https://github.com/AkariAsai/extractive_rc_by_runtime_mt . In the SQuAD dataset, the input is a question-paragraph pair in English and the output is the location of the answer in the paragraph. The 9 datasets correspond to the 9 combinations where the paragraph is in one language (among French, Japanese and English) and the question is in another language (among the same three possibilities).

If you use these datasets, please cite this paper : https://arxiv.org/abs/1910.04659 and the references mentioned above. 

## Results

In our paper "Multilingual Question Answering from Formatted Text applied to Conversational Agents", we trained multilingual BERT (https://github.com/google-research/bert) on the English training SQuAD v2.0 and we tested it on the 9 datasets mentioned above. 

We compare the performances of mBERT on the monolingual French and Japanese test sets with a previously published baseline (https://github.com/AkariAsai/extractive_rc_by_runtime_mt): 

<table>
  <tr>
    <td></td>
    <td colspan="2">French</td>
    <td colspan="2">Japanese</td>
  </tr>
  <tr>
    <td></td>
    <td>F1</td>
    <td>EM</td>
	<td>F1</td>
	<td>EM</td>
  </tr>
  <tr>
    <td>Baseline</td>
    <td>61.88</td>
    <td>40.67</td>
	<td>52.19</td>
	<td>37.00</td>
  </tr>
  <tr>
    <td>Multilingual BERT</td>
    <td>76.65</td>
    <td>61.77</td>
	<td>61.83</td>
	<td>59.94</td>
  </tr>
</table>

We also discuss the impressive results of mBert on cross-lingual datasets :

<table>
  <tr>
    <td colspan="2">Question</td>
    <td colspan="2">En</td>
    <td colspan="2">Fr</td>
    <td colspan="2">Jap</td>
  </tr>
  <tr>
    <td colspan="2"></td>
    <td>F1</td>
    <td>EM</td>
    <td>F1</td>
    <td>EM</td>
    <td>F1</td>
    <td>EM</td>
  </tr>	
  <tr>
    <td></td>
    <td>En</td>
    <td>90.57</td>
	<td>81.96</td>
	<td>78.55</td>
	<td>67.28</td>
	<td>66.22</td>
	<td>52.91</td>
  </tr>
  <tr>
    <td>Context</td>
    <td>Fr</td>
    <td>81.10</td>
	<td>65.14</td>
	<td>76.65</td>
	<td>61.77</td>
	<td>60.28</td>
	<td>42.20</td>
  </tr>
  <tr>
    <td></td>
    <td>Jap</td>
    <td>58.95</td>
	<td>57.49</td>
	<td>47.19</td>
	<td>45.26</td>
	<td>61.83</td>
	<td>59.93</td>
  </tr>
</table>

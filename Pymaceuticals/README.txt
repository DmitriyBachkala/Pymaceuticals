Pymaceuticals

-------------------------

"keep=False" was implemented with the assistance of chat.openai.com

duplicate_mice = merged_data[merged_data.duplicated(subset=["Mouse ID", "Timepoint"], keep=False)]
duplicate_mouse_ids = duplicate_mice["Mouse ID"].unique()

duplicate_mouse_ids

-

code was found in chat.openai.com

    tumor_vol_data.append(subset_data)
    
    # Determine outliers using upper and lower bounds
    quartiles = subset_data.quantile([0.25, 0.5, 0.75])
    lower_quartile = quartiles[0.25]
    upper_quartile = quartiles[0.75]
    iqr = upper_quartile - lower_quartile
    lower_bound = lower_quartile - 1.5 * iqr
    upper_bound = upper_quartile + 1.5 * iqr

-

assistance to correct code through chat.openai.com

merged_data_capomulin = pd.merge(average_tumor_volume, mouse_metadata, on='Mouse ID')

# Calculate the correlation coefficient between mouse weight and average tumor volume
correlation_coefficient, _ = linregress(merged_data_capomulin['Weight (g)'], merged_data_capomulin['Tumor Volume (mm3)'])[:2]
slope, intercept, _, _, _ = linregress(merged_data_capomulin['Weight (g)'], merged_data_capomulin['Tumor Volume (mm3)'])
regression_line = slope * merged_data_capomulin['Weight (g)'] + intercept

plt.scatter(merged_data_capomulin['Weight (g)'], merged_data_capomulin['Tumor Volume (mm3)'])
plt.plot(merged_data_capomulin['Weight (g)'], regression_line, color='red')

-



# Train a custom NER

In order to train a custom NER model, you have to follow these steps.

## Create a custom dataset
I have extracted news snippets from InShorts website and added a custom text separator after each news snippet. You can also create a custom dataset in a similar way.

## Text Annotation
I have used a text annotator to perform annotation: [ner-annotator](https://tecoholic.github.io/ner-annotator/). Upload your text file here and then select "Custom String" as text separator. Add new tags based on your task requirement. Click on the specific tag and then select part of the text which you want to annotate.

## Model Training
First, open this link: [https://spacy.io/usage/training](https://spacy.io/usage/training) and then fill the form to build your config_base.cfg file. Now, download the base model (check base model in `vectors` in config_base.cfg file).
Second, run `init fill-config` command to fill in the remaining defaults.
Now, train the model.

Note: If you don't have test dataset, you can mention `./train.spacy` inplace of `./dev.spacy` after `--paths.dev`. Also, to reduce number of training steps, you can edit `max_steps` in config.cfg file.

## Model Testing
Load the best model from `./output` directory and then test it using Spacy's NER module.
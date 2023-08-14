
# Train a custom NER Model

In order to train a custom NER model, you have to follow these steps.

## Create a custom dataset
I have extracted news snippets from the InShorts website and added a custom text separator after each news snippet. You can also create a custom dataset in a similar way.

## Text Annotation
I have used a text annotator to perform annotation: [ner-annotator](https://tecoholic.github.io/ner-annotator/). Upload your text file here and then select "Custom String" as a text separator. Add new tags based on your task requirement. Click on the specific tag and then select part of the text which you want to annotate.

## Model Training
First, open this link: [https://spacy.io/usage/training](https://spacy.io/usage/training) and then fill the form to build your config_base.cfg file. Now, download the base model (check base model in `vectors` in config_base.cfg file).
Second, run `init fill-config` command to fill in the remaining defaults.
Now, train the model.

_Note: If you don't have test dataset, you can mention `./train.spacy` in place of `./dev.spacy` after `--paths.dev`. Also, to reduce the number of training steps, you can edit `max_steps` in config.cfg file._

## Model Testing
Load the best model from `./output` directory and then test it using Spacy's NER module.

_Note: Run `custom-ner.ipynb` notebook for model training and testing of custom NER model._

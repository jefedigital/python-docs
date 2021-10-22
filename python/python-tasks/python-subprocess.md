# Python - subprocess

campaign\_query = "twurl -H '" + api\_base\_url + "' -X GET '" + campaign\_url + "'"

campaigns = json.loads(**subprocess**.check\_output(campaign\_query, shell=True))

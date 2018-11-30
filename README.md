# ai-banker

## Install requirements

In R console:

    install.packages("shiny")
    
    url <- "sandbox.apis.op-palvelut.fi/v1/accounts"
raw.result <- GET(url = url)
names(raw.result)

head(raw.result$headers)

this.raw.content <- rawToChar(raw.result$content)
nchar(this.raw.content)


this.content <- fromJSON(this.raw.content)
this.content.df <- do.call(what = "rbind",
                           args = lapply(this.content, as.data.frame))

head(this.content.df)

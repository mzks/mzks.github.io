# ROOT note

## Histgram

```C++
//Constructer
auto h = new TH1D("name","title",bin,min,max);

//Fill
h->Fill(data);

//Draw
h->Draw();
```

## Graph
```C++
//Prepare data
vector<Double_t> x = {1.0 ,2.0, 3.0);
vector<Double_t> y = {1.0 ,4.0, 9.0);

//Constructer
auto g = new TGraph(x.size(), x.data(), y.data());

//Draw
g->Draw();
```

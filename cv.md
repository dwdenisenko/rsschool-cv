#_Denisenko Denis_

## *Contacts for communication:*
* #### Phone: +7(983)178-~~00-00~~ 
* #### Email: dwdenisenko@gmail.com
* #### Telegram: _@hiddenis_

## *About Me:*

I started to study web development in my first years of university,
at the same time I was doing a little freelancing. During his studies,
he successfully completed an internship in web application development,
but continued his studies at the university. In the last courses of the university,
he decided to develop only on the web and moved to a company where there was only
web development.

## *Skills:*
TypeScript(Angular), PHP(Laravel)

## *Code examples:*
```
getAll(): Observable<LinkCategory[]> {
    if (this.linkCategories) {
        return new Observable(subscriber => {
            subscriber.next(this.linkCategories);
            subscriber.complete();
        });
    }
    if (!this.linkCategoriesSubject) {
        const subject: Subject<LinkCategory[]> = new Subject();
        this.linkCategoriesRepository.getAll().subscribe({
            next: categories => {
                this.updateLinkCategories(categories);
                subject.next(categories);
                subject.complete();
            },
                error: e => {
                subject.error(e);
            }
        });
        this.linkCategoriesSubject = subject;
    }

    return this.linkCategoriesSubject;
}

```

